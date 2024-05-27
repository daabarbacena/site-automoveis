<img style="margin-bottom:100px; object-fit: contain" width=100% src="/Captura de tela 2024-05-26 222840.png" />

<h1 align="center">Website of a Car Dealership</h1>

<h2>Project Summary:</h2>
<p>This is a project I completed for the "jQuery Plugins" module of the Full Stack JavaScript course at EBAC. The goal was to create a functional website for a car dealership using various jQuery plugins.</p>

<h2>My Key Learnings</h2>
<ul>
  <li>
    <h3>Hamburguer menu:</h3>
    <p>I implemented a hamburger menu using a series of <span> elements to create a clickable trigger. This menu is commonly used in mobile layouts to show or hide the navigation bar. Media queries are employed to control the initial display state       ("display: block" within the query and "display: none" outside). Functionality is achieved through jQuery's click and slideToggle functions. click fires a custom function when the menu is clicked, and slideToggle animates the navigation bar on      subsequent clicks (slide down on first click, slide up on second click).</p>
               
    $(".menu-hamburguer").click(function() {
        $("nav").slideToggle();
    });
    
  </li>
</ul>
<ul>
  <li>
    <h3>Carousel:</h3>
    <p>I utilized the "slick" carousel library to display a sequence of images with automatic sliding enabled by the "autoplay: true" setting. The process involves linking the images within a HTML <div> and initializing the carousel using the slick     plugin in the script.</p>

    $('#carousel-imagens').slick({
        autoplay: true
    });
    
  </li>
</ul>
<ul>
  <li>
    <h3>Form Validation:</h3>
    <p>I employed the "jquery validation" plugin to establish validation rules for the website's contact form. These rules ensure proper user interaction and guide users in completing required fields. For instance, if the name field is left blank,       an error message ("Please, insert your name") will appear beneath the input field. Additionally, a general alert pops up for any incomplete form submission, indicating the number of missing fields. This functionality is achieved through a           combination of boolean variables, a custom function to count invalid inputs, and conditional statements to trigger the alert message.</p>

    $("form").validate({
        rules: {
            nome:{
                required: true
            },
            email:{
                required: true,
                email: true
            },
            telefone:{
                required: true
            },
            mensagem: {
                required: true,
            },
            veiculoDeInteresse: {
                required: false,
            }
        },
        messages: {
            nome: "Por favor, insira o seu nome"
        },
        submitHandler: function(form){
            console.log(form)
        },
        invalidHandler: function(evento, validador) {
            let camposIncorretos = validador.numberOfInvalids();
            if (camposIncorretos) {
                alert(`Existem ${camposIncorretos} campos incorretos`)
            }
        }
    })
 
  </li>
</ul>

<ul>
  <li>
    <h3>Input masks:</h3>
    <p>Input masks enhance the user experience by providing a visual guide for data entry and automatically formatting user input (e.g., phone numbers). I implemented the "mask" plugin, which requires specifying the input element's ID along with         the desired mask format according to the plugin's documentation.</p>

    $("#telefone").mask("(00) 00000-0000");
    
  </li>
</ul>

<ul>
  <li>
    <h3>Smooth Scrolling and Auto-Field Population:</h3>
    <p>Clicking the "I'm Interested" button triggers a sequence of actions. First, it retrieves the closest element and stores the vehicle name in a variable. Next, it utilizes jQuery's animate function to smoothly scroll the user to the                 contact section and automatically populates the "Vehicle of Interest" field in the contact form with the retrieved vehicle name. The animation duration is set to 1000 milliseconds (1 second). The animate function requires both the scroll            direction and the target element.</p>

    $(".lista-veiculos button").click(function(){
        const destino = $("#contato");
        const nomeVeiculo = $(this).parent().find("h3").text();

        $("#veiculo-interesse").val(nomeVeiculo);

        $("html").animate({
            scrollTop: destino.offset().top
        }, 1000)
    })
    
  </li>
</ul>

<h2>References</h2>
<h4>The following resources were used throughout this project:</h4>
<table>
  <td>
    <a>Carousel</a>
  </td>
  <td>https://kenwheeler.github.io/slick/</td>
  <td>
    <a>Input Mask</a>
  </td>
  <td>https://igorescobar.github.io/jQuery-Mask-Plugin/</td>
  <td>
    <a>Form validate</a>
  </td>
  <td>https://jqueryvalidation.org</td>
</table>

<h2 align="center">If you wanna try this website just visit the following link:</h2>
<h3 align="center" href="https://site-automoveis.vercel.app">"https://site-automoveis.vercel.app"</h3>
