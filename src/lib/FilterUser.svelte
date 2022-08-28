<script>
    import { createEventDispatcher } from "svelte";

    //export let filter
    const dispatch = createEventDispatcher();
    
     const filter = (e) => {
dispatch('filter', e.target.value)
     }
</script>

<div class='ml-4 mt-4'>
    <label for='user-filter'> Filter User </label>
    <select 
    on:change={filter}
    name='user-filter' 
    class='border rounded-lg px-4 py-2 ml-4'>
      <option value='all'>All</option>
      <option value='active'>Active</option>
      <option value='inactive'>Inactive</option>
    </select>
  </div>