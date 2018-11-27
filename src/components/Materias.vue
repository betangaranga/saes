<template>
    <div>
    <md-table>
      <md-table-row>
        <md-table-head>Codigo Materia</md-table-head>
        <md-table-head>Materia</md-table-head>
        <md-table-head>Profesor</md-table-head>
        <md-table-head>Area</md-table-head>
      </md-table-row>
      <md-table-row v-for="materia in materias">
        <md-table-cell><p>{{materia.id}}</p></md-table-cell>
        <md-table-cell>{{materia.Name}}</md-table-cell>
        <md-table-cell>{{materia.Sem1.Teacher.Name}} {{materia.Sem1.Teacher.LastN}}</md-table-cell>
        <md-table-cell>{{materia.Area}}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
  </div>
</template>
<script>
import { db } from '../main'

export default {
     data() {
    return {
      materias:[
         
      ]    }
  },
  firestore(){
      return{
      materias:db.collection("Subjects").where("Area","==","Ingenieria")
  }
  },
  mounted(){
  }
}
</script>
<style>

</style>
