<script>
    let name
    let beltColor
    let age

    // let fightingCheck = false
    // let defendingCheck = false
    let skills = []

    const handleSubmit = () => {
        console.log(name, beltColor, age, skills)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="belt color" bind:value={beltColor}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <!-- <input type="checkbox" bind:checked={fightingCheck}>fighting<br>
    <input type="checkbox" bind:checked={defendingCheck}>defending<br> -->
    <input type="checkbox" bind:group={skills} value="fighting">fighting<br>
    <input type="checkbox" bind:group={skills} value="defending">defending<br>
    <label>Belf Color:</label>
    <select bind:value={beltColor}>
        <option value="green">green</option>
        <option value="black">black</option>
        <option value="red">red</option>
    </select>
    <button>Add person</button>
</form>

<style>

</style>