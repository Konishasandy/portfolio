// Mobile Menu

const menuBtn = document.getElementById("menuBtn");
const navLinks = document.getElementById("navLinks");

menuBtn.addEventListener("click", () => {
    navLinks.classList.toggle("active");
});


// Smooth Scroll

document.querySelectorAll('a[href^="#"]').forEach(link => {

    link.addEventListener("click", function(e){

        e.preventDefault();

        document.querySelector(this.getAttribute("href"))
        .scrollIntoView({
            behavior:"smooth"
        });

        navLinks.classList.remove("active");
    });
});


// Contact Form Validation

const form = document.querySelector("form");

form.addEventListener("submit",(e)=>{

    e.preventDefault();

    const name =
    document.querySelector('input[type="text"]').value;

    const email =
    document.querySelector('input[type="email"]').value;

    if(name === "" || email === ""){
        alert("Please fill all fields");
        return;
    }

    alert("Message Sent Successfully!");
    form.reset();
});
