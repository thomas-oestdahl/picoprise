<script>
    import { PublicClientApplication } from "@azure/msal-browser";
    import { account, token } from "../store/userInfo.js";

    const MSAL_CONFIG = {
        auth: {
            clientId: "480970cf-e49f-47d3-b1ce-ed2ab64ba425",
            redirectUrl: "localhost:5173/login/redirect",
            authority: "https://logintretoen.b2clogin.com/logintretoen.onmicrosoft.com/B2C_1_LoginOrSignup",
            knownAuthorities: ["https://logintretoen.b2clogin.com"]
        },
        cache: {
            cacheLocation: "sessionStorage", // This configures where your cache will be stored
            storeAuthStateInCookie: false, // Set this to "true" if you are having issues on IE11 or Edge
        },
        system: {
            loggerOptions: {
                loggerCallback: (level, message, containsPii) => {
                    if (containsPii) {
                        return;
                    }
                    console.warn(message);
                },
            },
        },
    };

    const msal = new PublicClientApplication(MSAL_CONFIG);
    msal.initialize();

    const handleResponse = (response) => {
        if (response !== null) {
            account.set(response.account);
            token.set(response.idToken);
        } else {
            account.set(getAccount());
        }

        if ($account) {
            console.log("YEY");
        }
    }

    const login = () => {
        msal.loginPopup().then(handleResponse).catch(console.error);
    }

    const getAccount = () => {
        // need to call getAccount here?
        const currentAccounts = msal.getAllAccounts();
        if (currentAccounts === null) {
            console.log("No accounts detected");
            return null;
        }

        if (currentAccounts.length > 1) {
            // Add choose account code here
            console.log("Multiple accounts detected, need to add choose account code.");
            return currentAccounts[0];
        } else if (currentAccounts.length === 1) {
            return currentAccounts[0];
        }

        return null;
    }
</script>

<button class="btn btn-accent" on:click={login}>Login</button>
