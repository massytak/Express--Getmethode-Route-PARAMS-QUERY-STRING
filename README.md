# Express--Getmethode-Route-PARAMS-QUERY-STRING
const express=require('express'); 
const app =express(); 
const hbs=require('hbs')
app.set('view engine','hbs')

app.get('/', function(req,res,next){
    console.log(req);
    
})

app.get('/user/:userb',function(req,res,next){
    
    console.log('username=',req.params.userb)
    
})
app.get('/index',function(req,res,next){
    
    res.render('index',{})
})
app.get('/result',(req,res,next)=>{
    let dates=req.query.startdate
    let city=req.query.city 
    res.render('result', {date : dates,citys:city})
    
    console.log('ladate =',dates , city);
})

app.listen(3000, function (){console.log('je suis dans le serveur!🤴')})