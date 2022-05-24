<template>
  <div class="submit-form">
    <div v-if="!submitted">
    <h3>Nuevo mission Commander</h3>
      <div class="form-group">
        <label for="title">Nombre </label>
        <input
          type="text"
          class="form-control"
          id="title"
          required
          v-model="missionCommander.name"
          name="title"
        />
      </div>
      <div class="form-group">
        <label for="title">Username</label>
        <input
          type="text"
          class="form-control"
          id="username"
          required
          v-model="missionCommander.username"
          name="username"
        />
      </div>
      <div class="form-group">
        <label for="title">Main Stack</label>
        <input
          type="text"
          class="form-control"
          id="mainStack"
          required
          v-model="missionCommander.mainStack"
          name="mainStack"
        />
      </div>
      <div class="form-group">
        <label for="title">Current Enrollment</label>
        <input
          type="checkbox"
          checked="checked"
          class="form-control"
          id="currentEnrollment"
          required
          v-model="missionCommander.currentEnrollment"
          name="currentEnrollment"
        />
      </div>
      <div class="form-group">
        <label for="title">Has Azure Certification</label>
        <input
          type="checkbox"
          checked="checked"
          class="form-control"
          id="hasAzureCertification"
          required
          v-model="missionCommander.hasAzureCertification"
          name="hasAzureCertification"
        />
      </div>
      <button @click="saveMissionCommander" class="btn btn-success">Agregar</button>
    </div>
    <div v-else>
      <h4> Mission Commander creado exitosamente. </h4>
      <button class="btn btn-success" @click="newMissionCommander">Add</button>
    </div>
  </div>
</template>

<script>
import missionCommanderService from "../services/missionCommanderService";
export default {
  name: "add-missionCommander",
  data() {
    return {
      missionCommander: {
        id: null,
        name: "",
        username: "",
        mainStack: "",
        currentEnrollment: Boolean,
        hasAzureCertification: Boolean
      },
      submitted: false
    };
  },
  methods: {
    saveMissionCommander() {
      var data = {
        name: this.missionCommander.name,
        username: this.missionCommander.username,
        mainStack: this.missionCommander.mainStack,
        currentEnrollment: this.missionCommander.currentEnrollment,
        hasAzureCertification: this.missionCommander.hasAzureCertification

      };
      missionCommanderService.create(data)
        .then(response => {
          this.missionCommander.id = response.data.id;
          this.submitted = true;
        })
        .catch(e => {
          console.log(e);
        });
    },
    newMissionCommander() {
      this.submitted = false;
      this.missionCommander = {};
    }
  }
};
</script>
