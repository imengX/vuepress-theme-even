<template>
  <div>
    <h1>{{$title}}</h1>
    <h2>{{$description}}</h2>
    <div v-for="page in $site.pages">
      <h2>{{page.title}}</h2>
      <p>desc</p>
    </div>
    <Content/>    
  </div>
</template>
 