Question 1 - Create an HTML page with a button . When the Button is Clicked, change the text of a paragraph element.

Solution -

```javascript
let btn = document.querySelector("button");
let p = document.querySelector("p");

btn.addEventListener("click", function () {
  p.textContent = "hey Hello hi hello hi";
});
```

Question 2 - Create a page with two images and a button. When the button is clicked, swap the source attribute of the images...

Solution -

```javascript
let btn = document.querySelector("button");
let img1 = document.querySelector("#img1");
let img2 = document.querySelector("#img2");

btn.addEventListener("click", function () {
  let src1 = img1.src;
  let src2 = img2.src;

  img1.src = src2;
  img2.src = src1;
});
```

Question 3 - Create a from with input fields and a submit button, Use JavaScript to validate the form and display an error message if the input is invalid.

```javascript
let form = document.querySelector("#form");
let input = document.querySelectorAll('input[type="text"]');
let h4 = document.querySelector("h4");

form.addEventListener("submit", function (event) {
  event.preventDefault();
  for (let i = 0; i < input.length; i++) {
    if (input[i].value.trim() === "") {
      h4.textContent = "Error , some like emty";
      h4.style.color = "red";
      break;
    }
  }
});
```

Question 4 - Create an unorderd list. Allow users to add and remove list items dynamically using buttons...

```javascript
let add = document.querySelector("#add");
let remove = document.querySelector("#remove");
let input = document.querySelector("input");
let ul = document.querySelector("ul");

let li;

add.addEventListener("click", function () {
  if (input.value.trim() === "") {
  } else {
    li = document.createElement("li");
    li.textContent = input.value;
    ul.appendChild(li);
    input.value = "";
  }
});

remove.addEventListener("click", function () {
  ul.removeChild(li);
});
```

Question 5 - Build a countdown timer that starts when a button is clicked and updates the display is real-time...

``` javascript
let start = document.querySelector('#start')
let stop = document.querySelector('#stop')
let h3 = document.querySelector('h3')

let Intr

start.addEventListener('click', function(){
   let count = 0;
   Intr = setInterval(function(){
      h3.textContent = count;
      count++;
   },1000)
})
stop.addEventListener('click', function(){
   clearInterval(Intr)
})

```

Question 6 - Create a tabbed interface where clicking on tabs displays different content sections without page rolead.

``` javascript
let home = document.querySelector("#home")
let about = document.querySelector("#about")
let contact = document.querySelector("#contact")

let hometext = document.querySelector("#hometext")
let abouttext = document.querySelector("#abouttext")
let contacttext = document.querySelector("#contacttext")

function saartexthato(){
   document.querySelectorAll('h3').forEach(function(h3){
      h3.style.display = 'none';
   })
}

home.addEventListener('click',function(){
   saartexthato()
   hometext.style.display = "block";
   hometext.style.width = "50%";
})

about.addEventListener('click',function(){
   saartexthato()
   abouttext.style.display = "block";
   abouttext.style.width = "50%";
})

contact.addEventListener('click',function(){
   saartexthato()
   contacttext.style.display = "block";
   contacttext.style.width = "50%";
})


```

Question 7 - Display a progress bar that updates in real-time, showing the progress of a task, download, or form submission.

``` javascript

let progress = document.querySelector("#progress")
let h3 = document.querySelector("h3")

let count  = 0

let int = setInterval(function(){

   if(count === 100){
    h3.style.opacity = 1;
      clearInterval(int)
   }
   count++;
   progress.style.width = count + "%";

      
},50)

```

Question 8 - Create a search bar that displays live search results as users type, updating the results without requiring a full page reload.

``` html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <link rel="stylesheet" href="style.css">
   <title>Document</title>
</head>
<body>

      <div id="main">
         <div class="container">
            <input type="text" placeholder="Search">
            <div class="people">
              

            </div>
         </div>
      </div>


   <script src="script.js"></script>
</body>
</html>
```


```css

*{
   margin: 0;
   padding: 0;
   box-sizing: border-box;
   font-family:  'gilroy';
}
html , body{
   width: 100%;
   height: 100%;

}
#main{
   width: 100%;
   height: 100%;
   background-color: #f1f1f1;

}
.container{
   padding: 10vw 25vw;


}
 input{
   width: 100%;
   padding: 12px 22px;
   font-size: 30px;
   font-weight: 500;
   border-radius: 10px;
   border: 1px solid royalblue;
   outline-color: royalblue ;
 }
 .people{
   display: flex;
   gap: 20px;
   flex-wrap: wrap;
   justify-content: center;
   margin-top: 30px;
 }
 .person{
   width: fit-content;
   display: flex;
   flex-direction: column;
   align-items: center;
 }
 .img{
   border-radius: 50%;
   border: 2px solid #dadada;
   width: 7vw;
   height: 7vw;
   overflow: hidden;
 }

 .img img{
   width: 100%;
   height: 100%;
   object-fit: cover;
 }


```



``` javascript


let input = document.querySelector("input");
let people = document.querySelector('.people');

let data = [
{name: "harsh" , src: "https://images.unsplash.com/photo-1715838854648-ea200803934a?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDEwfHRvd0paRnNrcEdnfHxlbnwwfHx8fHw%3D"},
{name: "rohit" , src: "https://images.unsplash.com/photo-1480455624313-e29b44bbfde1?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"},
{name: "rahol" , src: "https://images.unsplash.com/photo-1484515991647-c5760fcecfc7?q=80&w=1949&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"},
{name: "shyam" , src: "https://images.unsplash.com/photo-1492288991661-058aa541ff43?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"},

]

let pers = "";

data.forEach(function(elem){
  pers += ` <div class="person">
 <div class="img">
    <img src="${elem.src}" alt="">
 </div>
 <h4>${elem.name}</h4>
</div>
`

})

people.innerHTML = pers;

input.addEventListener("input",function(){
  let matching =  data.filter(function(elem){
      return elem.name.startsWith(input.value)
   })

   let newUsers = "";

   matching.forEach(function(elem){
      newUsers += ` <div class="person">
     <div class="img">
        <img src="${elem.src}" alt="">
     </div>
     <h4>${elem.name}</h4>
    </div>
    `
    
    })
    
    people.innerHTML = newUsers;
})

```


# Mastering-Practical-development-challenges
