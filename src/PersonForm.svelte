<script>
    import { createEventDispatcher } from "svelte";

    let dispatch = createEventDispatcher()

    let person_name;
    let belt_color;
    let age;
    let skills = [];

    const handleSubmit = () => {
        // console.log(person_name, belt_color, age, skills);
        const person = {
            name: person_name,
            beltColor: belt_color,
            age: age,
            skills: skills,
            id: Math.random()
        }
        dispatch('addPerson', person)
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={person_name} />
    <input type="number" placeholder="age" bind:value={age} />
    <label for="skill">Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting" />Fighting<br />
    <input type="checkbox" bind:group={skills} value="tracking" />Tracking<br />
    <input type="checkbox" bind:group={skills} value="running" />Running<br />
    <label for="belt-color">Belt color</label>
    <select bind:value={belt_color}>
        <option value="blue">Blue</option>
        <option value="green">Green</option>
        <option value="yellow">Yellow</option>
    </select>
    <button>Add person</button>
</form>
