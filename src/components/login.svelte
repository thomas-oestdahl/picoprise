<script>
    import { PublicClientApplication } from "@azure/msal-browser";
    import { account, token } from "../store/userInfo.js";

    const MSAL_CONFIG = {
        auth: {
            clientId: "bfc06977-9a0d-4e89-b0b6-ca82034530f5",
            redirectUrl: "localhost:5173/login/redirect",
            authority: "https://login.microsoftonline.com/50afee79-3902-4a04-bf79-718a413783dd",
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
