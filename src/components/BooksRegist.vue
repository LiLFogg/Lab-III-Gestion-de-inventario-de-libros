<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <div class="form-books">
    <form>
      <p >Registre un Libro: <br/> {{errorMessage}}</p>

      <label for="name">Nombre: </label>
      <input type="text" placeholder="Nombre" id="name" v-model="name" autocomplete="off" /><br/>

      <label for="author">Autor: </label>
      <input type="text" placeholder="Autor" id="author" v-model="author"> <br/>

      <label for="year">Año: </label>
      <input type="text" placeholder="Año de Publicación" id="year" v-model="year"><br/>

      
      <button class="button" type="submit" v-on:click="onSubmit">
        Registrar Libro
      </button>
    </form>
  </div>
  <h3>Registro de Libros</h3>
    
  <div class="book-list">
    <p >Libros Registrados:</p>
    <div class="table">
    <table id="Table">
      <tr>
        <th>Nombre</th>
        <th>Autor</th>
        <th>Año public.</th>
      </tr>
      <tr v-for="(book, index) in books" :key="index">
        <th> {{book.name}} </th>
        <th>{{ book.author }} </th>
        <th> {{book.year}} </th>
      </tr>
    </table>
  </div>
  </div>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    props: {
      title: String
    },

    data() {
      return {
        name: "",
        author: "",
        year: "",
        books: JSON.parse(localStorage.getItem('books')) || [],
        errorMessage: "",
        
      };
    },

    methods: {
      onSubmit() {
        if (
          this.name.trim() == "" ||
          this.author.trim() == "" ||
          this.year.trim() == ""  ||
          isNaN(this.year)
        ) {
          this.errorMessage = "Por favor complete todos los campos";
          
        } else {
          let bookRegist = {
            name: this.name,
            author: this.author,
            year: this.year,
          };
          if (!this.books.some(book => book.name === bookRegist.name && book.author === bookRegist.author && book.year === bookRegist.year)) {
            this.books.push(bookRegist);
          }
          else{
            this.errorMessage = "El libro ya se encuentra registrado";
            
          }
          localStorage.setItem('books', JSON.stringify(this.books));

          this.name = "";
          this.author = "";
          this.year = "";
        }
      },
    },
  }
</script>


<style scoped>
table {
  display: table-cell;
  table-layout: auto;
  column-rule-style: solid;
  column-rule-width: 1px;
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 0px;
  padding-right: 80px ;
  border-style: solid;
  background-color: rgba(179, 179, 179, 0.671);
  height: 40px;
  text-align: center;
}

th {
  margin-bottom: 20px;
  padding-left: 60px;
}

h3 {
  margin: 40px 0 0;
  text-decoration: underline;
  padding-left: 25px;
  font-weight: 200;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
h1{
  text-align: center;
  text-decoration: underline;
}

.button {
  margin-left: 250px;
  background-color: #65c516;
  border-radius: 5px;
  font-size: 18px;
  width: 150px;
  height: 60px;
  color: white;
  padding-left: 10px;
  box-shadow: inset 0 -0.6em 1em -0.35em rgba(0, 0, 0, 0.17),
    inset 0 0.6em 2em -0.3em rgba(255, 255, 255, 0.15),
    inset 0 0 0em 0.05em rgba(255, 255, 255, 0.12);
  text-align: center;
  cursor: pointer;
}
.book-list{
  background: linear-gradient(-90deg, #d0e7047c, #e948176b);
  border: 2px solid #d8d8d8;
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  display: flex;
  flex-direction: column;
  margin: 20px;
  margin-right: 250px;
  padding: 20px;
  width: 750px;
  font-size: 25px;
  text-align: justify;
}
.form-books {  
  background: linear-gradient(-90deg, #d0e7047c, #e948176b);
  border: 2px solid #d8d8d8;
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  display: flex;
  flex-direction: column;
  margin: 20px;
  margin-right: 25px;
  padding: 20px;
  width: 450px;
  font-size: 25px;
  text-align: justify;
}
</style>
