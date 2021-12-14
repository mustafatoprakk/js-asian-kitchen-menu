![asiankitchen](https://user-images.githubusercontent.com/37051222/145987198-8a216115-d153-48a1-a73c-1a7e4d0c62db.png)


## html
```
<body onload="getAll()">
    
    <div class="container pt-3">
        <div class="text-center py-3">
            <h1 class="t1-color font-corinthia" >Asian Kitchen's Menu</h1>
            <div class="pt-4">
                <button class="btn btn-outline-dark me-2 font-roboto" id="all_menu">All</button>
                <button class="btn btn-outline-dark me-2 font-roboto" id="korea_menu">Korea</button>
                <button class="btn btn-outline-dark me-2 font-roboto" id="japan_menu">Japan</button>
                <button class="btn btn-outline-dark font-roboto" id="china_menu">China</button>
            </div>
        </div>
        <div>
            <div class="row pt-5" id="menu_list">
                
            </div>
        </div>
    </div>
</body>
```



### js
```
let menu=[
    {
        id:1,
        title:"Tteokbokki",
        desc:"Spicy rice cakes, serving with fish cake.",
        price:11.50,
        category:"Korea",
        img:"https://twoplaidaprons.com/wp-content/uploads/2020/09/tteokbokki-top-down-view-of-tteokbokki-in-a-bowl-500x500.jpg"
    },
    {
        id:2,
        title:"Bibimbap",
        desc:"Boiling vegetables, serving with special hot sauce",
        price:11.50,
        category:"Korea",
        img:"https://www.forkknifeswoon.com/wp-content/uploads/2014/10/simple-homemade-chicken-ramen-fork-knife-swoon-01.jpg"
    },
    {
        id:3,
        title:"Jajangmyeon",
        desc:"Black bean sauce noodle, serving with green onion",
        price:11.50,
        category:"Korea",
        img:"https://www.curiouscuisiniere.com/wp-content/uploads/2020/04/Jajangmyeon-Korean-Noodles-in-Black-Bean-Sauce5.1200H-720x540.jpg"
    },
    {
        id:4,
        title:"Chicken Ramen",
        desc:"Chicken noodle soup, serving with vegetables such as soy bean, green onion. In an optional you can ask for egg.",
        price:11.50,
        category:"Japan",
        img:"https://www.savingdessert.com/wp-content/uploads/2019/02/Dan-Dan-Noodles-10.jpg"
    },
    {
        id:5,
        title:"Doroyaki",
        desc:"Red bean paste dessert, serving with honey.",
        price:11.50,
        category:"Japan",
        img:"https://www.justonecookbook.com/wp-content/uploads/2011/10/Dorayaki-New-500x400.jpg"
    },
    {
        id:6,
        title:"Onigiri",
        desc:"Rice Sandwich, serving with soy sauce",
        price:11.50,
        category:"Japan",
        img:"https://www.manusmenu.com/wp-content/uploads/2017/08/Onigiri-3-1-of-1.jpg"
    },
    {
        id:7,
        title:"Dan Dan Mian",
        desc:"Dan dan noodle, serving with green onion",
        price:11.50,
        category:"China",
        img:"https://dwellbymichelle.com/wp-content/uploads/2020/05/DWELL-bibimbap.jpg"
    },
    {
        id:8,
        title:"Yangzhou Fried Rice",
        desc:"Yangzhou style fried rice, serving with bean and pickles",
        price:11.50,
        category:"China",
        img:"https://salu-salo.com/wp-content/uploads/2013/02/Yangzhou-Fried-Rice1.jpg"
    },
    {
        id:9,
        title:"Ma Yi Shang Shu",
        desc:"Hot pepper sauce noodle, serving with soy bean and onion",
        price:11.50,
        category:"China",
        img:"https://assets.tmecosys.com/image/upload/t_web767x639/img/recipe/ras/Assets/F688C2F6-86EC-46C4-B9C7-A6BA01DF7437/Derivates/32E3E72A-F786-406D-AF7F-B30980A9AC6C.jpg"
    }
];

const allMenu=document.querySelector("#all_menu")
const koreaMenu=document.querySelector("#korea_menu")
const japanMenu=document.querySelector("#japan_menu")
const chinaMenu=document.querySelector("#china_menu")

const menuList=document.querySelector("#menu_list")


allMenu.addEventListener("click",getAll)
koreaMenu.addEventListener("click",getKorea)
japanMenu.addEventListener("click",getJapan)
chinaMenu.addEventListener("click",getChina)

function getAll(){
    menu.map(item=>{
        menuList.innerHTML+=`
        <div class="col-md-6 my-3">
            <div class="row">
                <div class="col-4">
                    <img width="100px" height="100px" src="${item.img}" alt="Tteokbokki" class="photo">
                </div>
                <div class="col-8">
                    <div class="menu-title font-roboto title-color">
                        <h4>${item.title}</h4>
                        <h4 class="">${item.price}</h4>
                    </div>
                    <div class="pt-3">                                
                        <p class="font-roboto">${item.desc}</p>
                    </div>
                </div>
            </div>
        </div>
        `
    })
}

function getKorea(){
    menuList.innerHTML=""
    menu.filter(item=>item.category==="Korea").map(item=>{
        menuList.innerHTML+=`
        <div class="col-md-6 my-3">
            <div class="row">
                <div class="col-4">
                    <img width="100px" height="100px" src="${item.img}" alt="Tteokbokki" class="photo">
                </div>
                <div class="col-8">
                    <div class="menu-title font-roboto title-color">
                        <h4>${item.title}</h4>
                        <h4 class="">${item.price}</h4>
                    </div>
                    <div class="pt-3">                                
                        <p class="font-roboto">${item.desc}</p>
                    </div>
                </div>
            </div>
        </div>
        `
    })
}

function getJapan(){
    menuList.innerHTML=""
    menu.filter(item=>item.category==="Japan").map(item=>{
        menuList.innerHTML+=`
        <div class="col-md-6 my-3">
            <div class="row">
                <div class="col-4">
                    <img width="100px" height="100px" src="${item.img}" alt="Tteokbokki" class="photo">
                </div>
                <div class="col-8">
                    <div class="menu-title font-roboto title-color">
                        <h4>${item.title}</h4>
                        <h4 class="">${item.price}</h4>
                    </div>
                    <div class="pt-3">                                
                        <p class="font-roboto">${item.desc}</p>
                    </div>
                </div>
            </div>
        </div>
        `
    })
}

function getChina(){
    menuList.innerHTML=""
    menu.filter(item=>item.category==="China").map(item=>{
        menuList.innerHTML+=`
        <div class="col-md-6 my-3">
            <div class="row">
                <div class="col-4">
                    <img width="100px" height="100px" src="${item.img}" alt="Tteokbokki" class="photo">
                </div>
                <div class="col-8">
                    <div class="menu-title font-roboto title-color">
                        <h4>${item.title}</h4>
                        <h4 class="">${item.price}</h4>
                    </div>
                    <div class="pt-3">                                
                        <p class="font-roboto">${item.desc}</p>
                    </div>
                </div>
            </div>
        </div>
        `
    })
}










```
