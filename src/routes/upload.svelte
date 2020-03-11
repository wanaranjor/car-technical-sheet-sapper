<script>
  import axios from 'axios';
  async function submitForm(event) {
    debugger
    const formData = new FormData(event.currentTarget);
    // console.log(event.currentTarget);
    const url = `http://localhost:3001/api/files/upload`;
    // await axios.post(url, formData);
    // console.log(response);
    // fetch(url, {
    //   method: 'POST',
    //   body: formData,
    // })

    await axios({
    method: 'post',
    url: url,
    data: formData,
    headers: {'Content-Type': 'multipart/form-data' }
    })
    .then(function (response) {
        //handle success
        console.log(response);
    })
    .catch(function (response) {
        //handle error
        console.log(response);
    });

  }
</script>

<form on:submit|preventDefault={submitForm} novalidate class="px-8 pt-6 pb-8 mb-4 bg-white rounded">
  <input type="file" name="files" />
  <button type="submit" class="bg-blue-500">
    Enviar
  </button>
</form>

