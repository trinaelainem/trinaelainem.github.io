<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Website</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://kit.fontawesome.com/c4254e24a8.js" crossorigin="anonymous"></script>
</head>
<body>
<div id="header">
    <div class="container">
        <nav>
            <img src="images/logo.jpg" class="logo">
            <ul id="sidemenu">
                <li><a href="#header">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
                <i class="fas fa-times" onclick="closemenu()"></i>
            </ul>
            <i class="fas fa-bars" onclick="openmenu()"></i>
        </nav>
        <div class="header-text">
            <p>An aspiring Software and Web Developer offering various software and web development services to help YOU with your needs!</p>
            <h1>Hello, I am <span>Trina Manaig</span>, at your service!</h1>
        </div>
    </div>
</div>
<!-- -----------about---------- -->
<div id="about">
    <div class="container">
        <div class="row">
            <div class="about-col-1">
                <img src="images/user.jpeg" class="user">
            </div>
            <div class="about-col-2">
                <h1 class="sub-title">Personal Background</h1>
                <p>I am an aspiring software and web developer currently taking up the Software and Web Development Program at Academy of Learning Career College in Victoria, British Columbia in Canada. I started this program last May 2023. So far, I have been proficient with various code programs. If you have further inquiries, please feel free to send me a message through the inquiry section, my email or my contact number located below. Thank you!</p>

                <div class="tab-titles">
                    <p class="tab-links active-link" onclick="opentab('skills')">Skills</p>
                    <p class="tab-links" onclick="opentab('experience')">Experience</p>
                    <p class="tab-links" onclick="opentab('education')">Education</p>
                </div>
                <div class="tab-contents active-tab" id="skills">
                    <ul>
                        <li><span>Software Development</span><br>Designing Web/App interfaces</li>
                        <li><span>Web Development</span><br>Web app Development</li>
                    </ul>
                </div>
                <div class="tab-contents" id="experience">
                    <ul>
                        <li><span>May 2023 - Present</span><br>Software and Web Development Program at AOLCC</li>
                    </ul>
                </div>
                <div class="tab-contents" id="education">
                    <ul>
                        <li><span>May 2023 - Present</span><br>Software and Web Development Program at AOLCC</li>
<!-- ---------services---------------- -->
<div id="services">
    <div class="container">
        <h1 class="sub-title">Current Services</h1>
        <div class="services-list">
            <div>
                <i class="fas fa-code"></i>
                <h2>Web Design</h2>
                <p>Creates the visual aspects of a website such as its layout and usability.</p>
            </div>
            <div>
                <i class="fas fa-crop-alt"></i>
                <h2>Software Development</h2>
                <p>Consults with clients, writes codes, solves compatibility issues, updates development process records, eliminating technical problems, and collaborates with the development team.</p>
            </div>
        </div>
    </div>
</div>
<!-- ----------contact------------- -->
<div id="contact">
    <div class="container">
        <div class="row">
            <div class="contact-left">
                <h1 class="sub-title">Contact Me</h1>
                <p><i class="fas fa-paper-plane"></i> manaigtrina@gmail.com</p>
                <p><i class="fas fa-phone-square-alt"></i> (250)883-2165</p>
            </div>
            <div class="contact-right">
                <form name="submit-to-google-sheet">
                    <input type="text" name="Name" placeholder="Name" required>
                    <input type="email" name="Email" placeholder="Email" required>
                    <input type="contact" name="Email" placeholder="Contact Number" required>
                    <textarea name="Message" rows="6" placeholder="Inquiry"></textarea>
                    <button type="submit" class="btn btn2">Submit</button>
                </form>
                <span id="msg"></span>
            </div>
        </div>
    </div>
</div>



<script>

    var tablinks = document.getElementsByClassName("tab-links");
    var tabcontents = document.getElementsByClassName("tab-contents");

    function opentab(tabname){
        for(tablink of tablinks){
            tablink.classList.remove("active-link");
        }
        for(tabcontent of tabcontents){
            tabcontent.classList.remove("active-tab");
        }
        event.currentTarget.classList.add("active-link");
        document.getElementById(tabname).classList.add("active-tab");
    }

</script>

<script>

    var sidemeu = document.getElementById("sidemenu");

    function openmenu(){
        sidemeu.style.right = "0";
    }
    function closemenu(){
        sidemeu.style.right = "-200px";
    }

</script>
<script>
    const scriptURL = '< add you own link here >' // add your own app script link here
    const form = document.forms['submit-to-google-sheet']
    const msg = document.getElementById("msg")
  
    form.addEventListener('submit', e => {
      e.preventDefault()
      fetch(scriptURL, { method: 'POST', body: new FormData(form)})
        .then(response => {
            msg.innerHTML = "Message sent successfully"
            setTimeout(function(){
                msg.innerHTML = ""
            },5000)
            form.reset()
        })
        .catch(error => console.error('Error!', error.message))
    })
  </script>
