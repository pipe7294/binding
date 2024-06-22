<template>
    <div id="binding">
        <form>
            <div>
                <label>Titulo:</label>
                <input type="text" v-model="titulo">
            </div>
            <div>
                <label>Emoji: </label>
                <select v-model="emoji">
                    <option value="🧑🏻‍💻">🧑🏻‍💻</option>
                    <option value="👾">👾</option>
                    <option value="👽">👽</option>
                    <option value="🤖">🤖</option>
                </select>
            </div>
            <div class="apreciacion">
                <label>Apreciacion</label>
                <ul>
                    <li>
                        <input type="radio" value="regular" name="apreciacion" v-model="apreciacion">
                        <label>regular</label>
                    </li>
                    <li>
                        <input type="radio" value="bueno" name="apreciacion" v-model="apreciacion">
                        <label>bueno</label>
                    </li>
                    <li>
                        <input type="radio" value="muy bueno" name="apreciacion" v-model="apreciacion">
                        <label>muy bueno</label>
                    </li>
                    <li>
                        <input type="radio" value="increible" name="apreciacion" v-model="apreciacion">
                        <label>increible</label>
                    </li>
                </ul>
            </div>
            <div>
                <label>Competencias aprendidas</label>
                <div class="competencias">
                    <ul>
                        <li>
                            <input type="checkbox" v-model="competencias" name="competencias" value="Morfologia de un componente">
                            <p>Morfologia de un componente</p>
                        </li>
                        <li>
                            <input type="checkbox" v-model="competencias" name="competencias" value="one-way y two-way data binding">
                            <p>One-way y Two-way Data-binding</p>
                        </li>
                        <li>
                            <input type="checkbox" v-model="competencias" name="competencias" value="patron de diseño MVVM">
                            <p>El patron de diseño MVVM</p>
                        </li>
                        <li>
                            <input type="checkbox" v-model="competencias" name="competencias" value="Directivas">
                            <p>Directivas</p>
                        </li>
                        <li>
                            <input type="checkbox" v-model="competencias" name="competencias" value="Estado">
                            <p>Estado</p>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="opinion">
                <label>Opinion</label>
                <textarea v-model="opinion" id="" rows="4"></textarea>
            </div>
        </form>
        <section>
            <h1>{{ emoji }}</h1>
            <h2>{{ titulo }}</h2>
            <h3>y me parece {{ apreciacion }}</h3>
            <h4>
                He aprendido:
                <p>{{ competencias }}</p>
            </h4>
            <h5>Mi opinión hasta ahora del framework es:</h5>
            <p>{{ opinion }}</p>

        </section>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            emoji: "",
            text: "",
            apreciacion: "",
            competencias: [],
            opinion: "",
        };
    },
};

</script>

<style>
body {
    padding: 10px;
}

#binding {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
    display: grid;
    gap: 10px;
    grid-template-columns: 300px 1fr;
}

form {
    background: black;
    color: white;
    padding: 30px;
    border-radius: 15px;
    display: flex;
    gap: 10px;
    flex-direction: column;
}

form>div {
    display: flex;
    gap: 10px;
}

form .competencias {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
}

form .competencias div {
    display: flex;
    align-items: flex-start;
    gap: 5px;
}

hr {
    width: 100%;
}

section {
    border: 1px solid;
    border-radius: 15px;
    padding: 0px 30px;
    text-align: center;
}

h1 {
    font-size: 60px;
}
</style>
