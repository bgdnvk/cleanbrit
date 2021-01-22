<script>
  let src = './images/building.png'
  import Option from './Option.svelte'
  import New from './New.svelte'
</script>

<div class="flex border-2	">
    <div class="flex-auto">
      <!-- Will grow and shrink as needed taking initial size into account -->
     <Option jobName='job name1' jobC='text content'></Option>

    </div>
    <div class="flex-auto">
      <!-- Will grow and shrink as needed taking initial size into account -->
      <Option jobName='job name1' jobC='text content'></Option>


    </div>
   
  </div>