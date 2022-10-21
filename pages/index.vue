<template>
  <div>
    <h2>
      Welcome to the best corny dad jokes on the web!
    </h2>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  head(){
        return {
            title: 'Main Page',
            meta:[
              {
                hid: 'description',
                name: 'description',
                content: 'Best place for dad jokes'
              }
            ]
        }
    }
}
</script>
