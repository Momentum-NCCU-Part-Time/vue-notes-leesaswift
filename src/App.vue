<script setup>
import { ref } from "vue";

let text = ref([]);
const newMsg = ref("");
const msgTitle = ref("");
const msgBody = ref("");

const displayMsg = () => {
  fetch("https://localhost:3000/notes", {
    method: "GET",
    headers: { "Content-Type": "application/json" },
  })
    .then((res) => res.json())
    .then((data) => {
      cosole.log(data);
      text.value = data;
    });
};
</script>
