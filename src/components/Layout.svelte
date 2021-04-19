<script>
	import Input from './Input.svelte' 
</script>

  <div class="wrapper">
    <header>Todo App</header>
	<br>
    <div>
      <Input />
    </div>
  </div>

<style>
.wrapper{
  background: #fff;
  max-width: 400px;
  width: 100%;
  margin: 120px auto;
  padding: 25px;
  border-radius: 5px;
  box-shadow: 0px 10px 15px rgba(0,0,0,0.1);
}
.wrapper header{
  font-size: 30px;
  font-weight: 600;
}
.wrapper .inputField{
  margin: 20px 0;
  width: 100%;
  display: flex;
  height: 45px;
}
</style>


