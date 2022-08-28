<script>
  import user1 from '../assets/images/user1.png'
  import user2 from '../assets/images/user2.png'
  import user3 from '../assets/images/user3.png'
  import User from './User.svelte'
  import FilterUser from './FilterUser.svelte'


  let users = [{
    id: 1,
    image: user1,
    name: "John",
    email: "John@gmail.com",
    active: false
  },
  {
    id: 2,
    image: user2, 
    name: 'Jack',
    email: "Jack@yahoo.com",
    active: true
  },
{
  id: 3,
  image: user3,
  name: 'Jim',
  email: 'jim@grubbrr.com',
  active: false
}];

let filteredUsers = users;

const filter = ({ detail }) => {
    if (detail === "null") {
      filteredUsers = users;
      return;
    }

    const active = detail === "true";
    filteredUsers = users.filter((user) => user.active === active);
  };
  </script>
  
  <!-- END OF SCRIPT TAG WITH JAVASCRIPT FUNCTIONS -->

  
  <div>
    <h1 class='text-2xl text-center mt-10'>List of Users</h1>

    <FilterUser on:filter{filter} />

    {#each filteredUsers as user, i (user.id)}
<User {user} {i}/>
    {:else}
    <p>No user found</p>
  {/each}
</div>
  
  