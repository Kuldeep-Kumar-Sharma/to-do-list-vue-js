<template>
  <to-do-list />
</template>

<script>
import ToDoList from './components/ToDoList.vue'

export default {
  name: 'App',
  components: {
    ToDoList
  }
}



/**
const express = require("express");


 *
 * @returns {express.Application}
 
const createExpressApp = () => {
  const app = express();
  app.get('*', function (req, res) {
    let operator = req.url.substring(req.url.indexOf('+'), req.url.indexOf('+') + 1);
    console.log(1);
    // let nums = req.url.split(operator);
    // let num1 = parseInt(nums[0].substring(1));
    // let num2 = parseInt(nums[0]);
    // let answer = "VALIDATION_ERROR";
    // switch(operator){
    //     case '+':
    //         answer = num1+num2;
    //     break;
    // }
    // console.log(answer);
    res.send({ "result": "" });
  });
  return app;
};
***/

</script>

