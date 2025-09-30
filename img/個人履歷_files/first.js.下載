let bar = document.querySelectorAll(".bar");
let bar1 = document.getElementsByClassName("bar1")[0];
let bar2 = document.getElementsByClassName("bar2")[0];
let bar3 = document.getElementsByClassName("bar3")[0];
let navbars = document.getElementsByClassName("navbars")[0];
let navblock = document.getElementsByClassName("navblock")[0];
let overlay = document.getElementsByClassName("overlay")[0];
let title = document.getElementsByClassName("title")[0];
let navBool = true;

navbars.addEventListener("click",function(event){
    event.stopPropagation();
    if(navBool){
        navblock.style.display = "block";
        bar1.style.transform = "rotate(45deg) translate(14px,12px)";
        bar2.style.display = "none";
        bar3.style.transform = "rotate(-45deg) translate(14px,-12px)";
        overlay.style.display = "block";
    }else{
        navblock.style.display = "none";
        bar1.style.transform = "rotate(0deg) translate(0)";
        bar2.style.display = "block";
        bar3.style.transform = "rotate(0deg) translate(0)";
        overlay.style.display = "none";
    }
    navBool = !navBool;
})

title.addEventListener("mouseover", function () {
    title.style.opacity = "1";
})
title.addEventListener("mouseout", function () {
    if(window.scrollY < 150){
        title.style.opacity = "1";
    }else{
        title.style.opacity = "0.5";
    }
})
// title.addEventListener("mouseleave", function () {
//     title.style.opacity = "0.5";
// })

window.addEventListener("scroll", () => {
    if(window.scrollY > 150){
        title.style.opacity = "0.5"
    }else{
        title.style.opacity = "1";
    }
});





/* 原本旋轉的元件在hover的時候加速 */ 



/* 數字的變化是從0~100，並且監聽滾輪(利用Y軸) */
function animateLoading(entry){
    const loading = entry.target;
    const text = loading.querySelector(".loadNumber");
    const target = parseInt(loading.getAttribute("data-target"));
    let current = 0;
    loading.style.width = target + "%";
    const duration = 5000;
    const stepTime = Math.floor(duration / target);
    const interval = setInterval(() => {
        if(current >= target) {
            clearInterval(interval);
            text.textContent = target + "%";
        }else{
            current++;
            text.textContent = current + "%";
        }
    }, stepTime);
}
const observer = new IntersectionObserver((entries, observer) =>{
    entries.forEach(entry => {
        if(entry.isIntersecting){
            animateLoading(entry);
            observer.unobserve(entry.target);
        }
    });
}, {
         threshold: 0.9
});


document.querySelectorAll(".loading").forEach(loading => {
    observer.observe(loading);
});







