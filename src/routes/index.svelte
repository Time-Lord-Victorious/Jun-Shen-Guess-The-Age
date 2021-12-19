<script>
    let name = " ";
    let age = " ";
    let count = " ";
    async function getname() {
       fetch('https://api.agify.io/?name=' + name)
       .then((response) => response.json())
       .then((data) => {
     age = data.age; 
     count = data.count; 
   });

}
</script>
<h1>Guess Age</h1>

<form on:submit|preventDefault={getname}>
    <label for="location">Name:</label>
    <input id="location" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>
<p>Age: {age}</p>
<p>Count: {count}</p>