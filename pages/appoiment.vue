<template>
  <v-container>
    <v-row class="texto">
      <v-col>
        <h3>Appoiment Management</h3>
      </v-col>
    </v-row>
    <v-row class="texto2">
      <v-col md="6">
        <v-btn class="boton1">
          Generate Report
        </v-btn>
        <v-text-field label="First Name" outlined />
        <v-text-field label="Email" outlined />
        <v-text-field label="NIC" outlined />
        <v-text-field label="Gender" outlined />
        <v-text-field label="Departament Name" outlined />
        <v-text-field label="Address" outlined />
      </v-col>
      <v-col md="4" class="columna2">
        <v-text-field class="renglon" label="Id" outlined />
        <v-text-field class="renglon1" label="Last Name" outlined />
        <v-text-field class="renglon2" label="Mobile Number" outlined />
        <v-text-field type="date" label="Date Birthay" outlined />
        <v-text-field type="data" label="Appoiment Date" outlined />
        <v-text-field type="datetime-local" label="Appoiment Time" outlined />
        <v-text-field label="Doctor Name" outlined />
      </v-col>
      <v-col md="2">
        <v-btn class="boton2">
          search
        </v-btn>
      </v-col>
      <v-btn class="boton3">
        Register
      </v-btn>
      <v-btn class="boton4">
        update
      </v-btn>
      <v-btn class="boton5">
        delete
      </v-btn>
    </v-row>
    <v-row class="texto3">
      <h3 class="titulo">
        Recent Appoiment
      </h3>
      <p class="parrafo">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto, culpa.
      </p>
      <v-simple-table class="tabla">
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Rol</th>
            <th>Gender</th>
            <th>Mobile Number</th>
            <th>NIC</th>
            <th>DOB</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in suppliers" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.rol }}</td>
            <td>{{ item.gender }}</td>
            <td>{{ item.number }}</td>
            <td>{{ item.nic }}</td>
            <td>{{ item.dob }}</td>
            <td>
              <v-btn icon small>
                <v-icon>mdi-status</v-icon>
              </v-btn>
              <v-btn icon small>
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </td>
          </tr>
        </tbody>
      </v-simple-table>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'InspirePage'
}
</script>

<style scoped>
.parrafo {
  margin-top: 6%;
}
.tabla {
  margin-top: 1%;
  width: 90%;
  margin-left: 3%;
  margin-right: 1%;
}
.titulo {
  margin-top: 1%;
  margin-left: 2%;
}
.v-btn.boton5 {
  background: linear-gradient(-90deg, #cb4545,#db1818);
  margin-left: 5%;
}
.v-btn.boton4 {
  background-color: #5634d1;
  margin-left: 5%;
}
.v-btn.boton3 {
  background: linear-gradient(-90deg, #34bf0a,#85d122);
  margin-left: 25%;
}
.custom-text-field .prefix-box {
  background-color: black; /* Fondo negro */
  color: white;           /* Texto blanco */
  padding: 5px 10px;      /* Espaciado interno */
  border-radius: 4px;     /* Bordes redondeados */
  font-weight: bold;      /* Negrita en el texto */
}
.v-btn.boton2 {
  background: linear-gradient(-90deg, #e9eb26,#faf53b);
  border-radius: 10px;
  margin-top: 25%;
}
.columna2 {
  margin-top: 3%;
}
.texto {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 1.6%;
  margin-right: 1.6%;
}

.texto2 {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 1.6%;
  margin-right: 1.6%;
  margin-top: 5%;
}
.texto3 {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 1.6%;
  margin-right: 1.6%;
  margin-top: 5%;
}

.boton1 {
  margin-top: 3%;
  margin-left: 3%;
  background: linear-gradient(-90deg,#7f7694, #8e81cc);
  border-radius: 10px;
  margin-bottom: 6%;
}
.renglon {
  width: 90%;
}
.renglon1 {
  width: 100%;
}
.renglon2 {
  width: 100%;
}

</style>
