<script>
  // @ts-nocheck

  export let label;
  export let placeholder;
  export let type;
</script>

<div class="form-control w-full max-w-sm">
  <label class="label" for={label}>
    {label}
  </label>
  <input
    {type}
    {placeholder}
    class="input input-bordered w-full max-w-sm"
    name={label}
  />
</div>
