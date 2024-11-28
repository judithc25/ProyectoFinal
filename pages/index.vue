<template>
  <v-container>
    <v-row class="primero">
      <v-col class="inicio" cols="2">
        <v-icon>mdi-account-injury</v-icon>
        <h5>Total Patient</h5>
      </v-col>
      <v-col class="inicio" cols="2">
        <v-icon>mdi-needle</v-icon>
        <h5>Total Doctors</h5>
      </v-col>
      <v-col class="inicio" cols="2">
        <v-icon>mdi-home</v-icon>
        <h5>Total Wards</h5>
      </v-col>
      <v-col class="inicio" cols="2">
        <v-icon>mdi-medication</v-icon>
        <h5>Total Labs</h5>
      </v-col>
    </v-row>
    <v-row class="texto">
      <h3 class="titulo">
        Recent Doctors
      </h3>
      <p class="parrafo">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto, culpa.
      </p>
      <v-simple-table class="tabla">
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Mobile</th>
            <th>Address</th>
            <th>Consultacy charge</th>
            <th>Education</th>
            <th>DOB</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in suppliers" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.mobile }}</td>
            <td>{{ item.address }}</td>
            <td>{{ item.consultacy }}</td>
            <td>{{ item.education }}</td>
            <td>{{ item.dob }}</td>
            <td>
              <v-btn icon small>
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </td>
          </tr>
        </tbody>
      </v-simple-table>
    </v-row>
    <v-row class="texto1">
      <h3 class="titulo">
        Out of Stock
      </h3>
      <p class="parrafo">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto, culpa.
      </p>
      <v-simple-table class="tabla">
        <thead>
          <tr>
            <th>ID</th>
            <th>Drug Name</th>
            <th>Expire Date</th>
            <th>Manufacture Date</th>
            <th>Price</th>
            <th>QTY</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in suppliers" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.date }}</td>
            <td>{{ item.mdate }}</td>
            <td>{{ item.price }}</td>
            <td>{{ item.qty }}</td>
            <td>
              <v-icon>mdi-status</v-icon>
            </td>
          </tr>
        </tbody>
      </v-simple-table>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style scoped>
.texto {
    background-color:rgb(247, 244, 241);
    border-radius: 13px;
    margin-left: 1.6%;
    margin-right: 1.6%;
    margin-top: 4%
  }
  .texto1 {
    background-color:rgb(247, 244, 241);
    border-radius: 13px;
    margin-left: 1.6%;
    margin-right: 1.6%;
    margin-top: 4%;
  }
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
.primero {
  margin-top: 2%;
}
.inicio {
  background-color:rgb(247, 244, 241);
  border-radius: 10px;
  margin-left: 6%;
}
</style>
