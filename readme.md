# Coder Academy - Portfolio Website Assessment

## Overview
This is a portfolio website for assessment purposes. Currently in development and will continue to add features in this readme that have been added to the website.

## Components
In the components added 2 which are the Header and the Footer. I added these to promote consistency across all the pages. The HTML portions have been added to each of the pages while the SCSS portions have been imported into each SCSS file of the corresponding page. 

### Header
In the header, I wanted to add a logo icon for the homepage and displayed on the top left corner while the rest of the contents of the navigation bar displayed on the top right corner. I also added feature where the contents would be displayed fully when in desktop view while when in mobile view the nav bar will condense into a hamburger icon. This will give the user the option to open the nav bar when required in mobile view. I also added font to standardise the pages for consistency. Please see code below:
```html
    <nav class="nav">
        <input type="checkbox" id="nav-checkbox"
        class="nav-checkbox">
        <label for="nav-checkbox" class="nav-toggle">
            <svg class="menu" viewbox="0 0 448 512"
            width="100" title="bars">
        <i class="fa-solid fa-bars"></i>
    </svg>
    
</label>
<ul class="nav-menu">
    <li><a href="../index.html"><i class="fa-solid fa-house"></i></a></li>
    <li><a href="./about.html">About Me</a></li>
    <li><a href="./passions.html">Passions</a></li>
    <li><a href="./experience.html">Experience</a></li>
    <li><a href="./contact.html">Contact Me</a></li>
</ul>
</nav>
```

Please see SCSS coding aswell 

```scss
*,
*::before,
*::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-weight: 700;
    height: 100vh;
}

.nav {
    

    &-toggle{
        position: absolute;
        cursor: pointer;
        margin: 0rem 1rem;
        right: 0;
        
        svg{
            width: 1.5rem;
            fill: black;
        }

        .menu{
            margin-top: 0.2rem;
        }
    }

    &-checkbox{
        display:none;
    }

    &-menu{
        display: flex;
        flex-direction: column;
        gap: 2rem;
        align-items: center;
        margin: 1rem;
    }

    li{
        list-style: none;
        display: none;
        background-color: $dark-background;
        padding: 10px;
        border-radius: 5px;
        color: $text-color;

        &:first-child{
           margin-right: auto; 
           display:block;
        }
    }

    a{
        text-decoration: none;
        color:inherit;
        font-size: 1.2rem;
    }

    svg{
        width: 1.5rem;
        fill: black;

    }
}

#nav-checkbox:checked ~ ul.nav-menu li{
    display:block;
}

#nav-checkbox:checked ~ label.nav-toggle .close{
    display:block;
}

#nav-checkbox:checked ~label.nav-toggle .menu{
    display:none;
}

@media only screen and (min-width:700px){
    .nav{
        &-toggle{
            display: none;
        }
        &-menu{
            flex-direction: row;

            li{
                display: block;
            }
        }
    }
}
```

### Footer
In the footer I have added the social media icons with links to the corresponding pages and details for contacts. With the icons I added some responsiveness through adding in some animation so that the icons when hovered over will change color and also rise abit. Please see code down below:
```html
    <footer>
       
        <div class="social-media">
            <a href="https://www.github.com" target="_blank">
                <i class="fa-brands fa-github" style="--fa-beat-fade-opacity: 0.67; --fa-beat-fade-scale: 1.075;" ></i>
            </a>
            <a href="https://www.linkedin.com" target="_blank">
                <i class="fa-brands fa-linkedin"></i>
            </a>
            <a href="https://www.instagram.com" target="_blank">
                <i class="fa-brands fa-instagram"></i>
            </a>
        </div>
        <div class="info">
            <p>Contact: 0404 123 456</p>
            <p>Address: 1 Street St, Suburb</p>
        </div>
</footer>
```

Please see SCSS coding for animation

```scss
footer {

    // @include background-stuff();
    bottom: 0;
    margin-top: 10px;

    p {
        padding: 20px;
        margin: 10px;
        font-size: 20px;
        letter-spacing: 2px;
        color: $text-color;
        background-color: $dark-background;
        border-radius: 10px;
        text-align: center;
        
    }
    
    .social-media {
        display: flex;
        justify-content: space-around;
        
        margin-bottom: 24px;
        
        a {
            i {
                color: $secondary-color;
                font-size: 24px;
                background-color: $dark-background;
                padding: 5px;
                margin-bottom: 10px;
                border-radius: 5px;
                transition: background 0.5s;
                transition: transform 0.5s;
                text-decoration: none;
                display: inline-block;
            }
            i:hover{
                color: $dark-background;
                background-color: $primary-color;
                transform: translateY(-5px);

            }
        }
    }
    
    .info {
        color: $secondary-color(41, 40, 40);
        
        
        p {
            margin: 5px 0;
        }
    }
}
```

## Defaults 
For the defaults I have added 2 which are the breakpoint and colors. I created these so that I can create consistency accross the pages with the color palette and how all the elements display when changing from desktop view to mobile view. These have been imported into each of the SCSS files of the corresponding pages.

### _Colors.scss

Added an scss file to have colors from selected palette beeasily accessed. Please see below SCSS code 

```scss
$primary-color: #D1C6C3;
$secondary-color: #E8E1D6;
$dark-background: #6E6966;
$primary-background: #9BA7AB;
$text-color: #DDD4CD;
```

### _Breakpoint.scss

Added an scss file to have set dimensions required when adjusting the elements of each individual page for when they are displayed in desktop or mobile view. Please see below SCSS code:

```scss
$medium: 600px;
```


## Pages

### Homepage
For the home page I wanted to add a simple introduction about myself. I added an image of myself as a center so that it gives a focal point to look on the page while leading down to my additional content. I also wanted to add some functionality to the page so that it provides responsiveness and also allows the user to navigate to the content they require with ease.

I added a button function within my name so that while the name stands out it also links to my "About me" page. Giving more functionality to the page. Please see below for HTML code:

```html
        <div class="header-text">
            <h1>Hi, I'm <span><a class="btn btn-link" href="./Pages/about.html">Patrick.</a></span><br>From Sydney, Australia</h1>
            <h3><span>Programmer</span></h3>
        </div>
```
Please see below SCSS code
```scss
body {
    background-image: url(../images/background-wihtewlight.jpg);
    background-size: cover;
    background-position: center;
}
.header-text{
    margin-top: 100px;
    font-size: 36px;
    display: flex;
    justify-content: center;

}
.header-text h1{
    font-size: 60px;
    margin-top: 20px;
    color: $dark-background;
    margin: 40px;
    font-weight: 700;
}


.header-text h1 span{
    color: $text-color;
    background: $dark-background;
    border-radius: 6px;
    padding: 5px;
}

.btn.btn-link{
    color: $text-color;
    text-decoration: none;
    transition: background 0.5s;

}

.btn.btn-link:hover{
    background: $primary-color;
    color: $dark-background;
    padding: 5px;
    border-radius: 6px;
    border: 1px solid $primary-color;
    text-decoration: none;
}

.header-text h3 span{
    color: $dark-background;
    border-radius: 6px;
    padding: 15px;
    margin-bottom: 60px;
}
```

Additionally to this page I wanted to add an image which gives the user a link to access my experiences page. I wanted it to be eye catching so I added some animation so that when the user hovers their mouse over the image it will entice the user to click the link to my projects. Please see the HTML code:
```html
        <h1 class="upcoming-projects">
            <div class="projects">
                <div class="work">
                    <img src="./styles/images/gamer.jpg">
                    <div class="layer">
                        <h3>Upcoming Projects</h3>
                        <p>Lorem ipsum dolor sit amet consectetur.</p>
                        <a href="./Pages/experience.html"><i class="fa-solid fa-up-right-from-square"></i></a>
                    </div>
                </div>
            </div>
        </h1>
```
Please see my SCSS code aswell
```scss
.work{
    border-radius: 10px;
    position: relative;
    overflow: hidden;
}
.work img{
    width: 100%;
    border-radius: 10px;
    display: block;
    transition: transform 0.5s;
}

.upcoming-projects{
    margin-bottom: 100px;
    margin-top: 100px;
}

.layer{
    width: 100%;
    height: 0;
    background: linear-gradient(rgba(0,0,0,0.6), $primary-color);
    border-radius: 10px;
    position: absolute;
    left: 0;
    bottom: 0;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 0 40px;
    text-align: center;
    transition: height 0.5s;
}

.layer h3{
    font-weight: 700;
    margin-bottom: 20px;
    font-size: 72px;
    color: $primary-color;
}

.layer p{
    font-size: 36px;
}

.layer a{
    margin-top: 20px;
    color: $dark-background;
    text-decoration: none;
    font-size: 36px;
    line-height: 60px;
    background: $secondary-color;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    text-align: center;
}

.work:hover img{
    transform: scale(1.1);
}

.work:hover .layer{
    height:100%

}
.main-image{
    display: flex;
    justify-content: center;
    height: 600px;
    margin-top: 100px;

}

@media screen and (min-width: 600px) {
    footer {
        .social-media {
            width: 50%;
            margin-left: auto;
            margin-right: auto;
        }
    }

        .nav-items {
            width: 50%;
        }
    
}
```

### About Page
For the About page I added an image and also some lorem ipsum text to fill out the page. I also added some links within the description text which links to other pages. I created 1 for Projects and another for Hobbies. I also added some animation so that the user knows that the link is responsive. Just to give the user portability to access the subject that interests them. Please see HTML code:
```html
    <section class="about">
        <div class="image">
            <img src="../styles/images/aboutphotoheadsmall.jpg">
        </div>
        
        <div class="main">
            <div class="about-text">
                <h2>About Me</h2>
                <h5>Developer</h5>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                    Vel hic corrupti similique veritatis distinctio delectus ipsa mollitia ipsam quam nam nulla perferendis, nobis cumque, quod libero numquam incidunt. 
                    <a class="btn" href="../Pages/experience.html">Projects</a> Recusandae, consectetur.Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                    Vel hic corrupti similique veritatis distinctio delectus ipsa mollitia ipsam quam nam nulla perferendis, nobis cumque
                    <a class="btn" href="../Pages/passions.html">Hobbies</a>, quod libero numquam incidunt. Recusandae, consectetur.
                </p>
            </div>
        </div>
    </section>
```
Please see SCSS code
```scss
.btn{
    background: $primary-color;
    border: 1px solid $primary-color;
    border-radius: 6px;
    color: $dark-background;
    font-weight: 700;
    text-decoration: none;
    padding: 1px;
    transition: background 0.5s;
}

.btn:hover{
    background: $primary-background;
    color: $text-color;
}
```
Please see SCSS code for the remainder of the page
```scss
body {
    background-image: url(../images/background-wihtewlight.jpg);
    background-size: cover;
    background-position: center;
}
section{
    display: flex;
    flex-direction: column;
}

.about {
    width: 100%;
    height: fit-content;
    padding: 100px 0px;

}

.about img {
    height: auto;
    width: auto;
    position: center;
    display: flex;

}

.about-text {
    width: 550px;
}

.main {
    width: auto;
    max-width: 95%;
    margin: 0 auto;
    display: block;
    align-items: center;
    justify-content: center;
}

.about-text h2 {
    color: $dark-background;
    font-size: 75px;
    text-transform: capitalize;
    margin-bottom: 10px;
    padding: 10px;
}

.about-text h5 {
    color: $dark-background;
    letter-spacing: 2px;
    font-size: 45px;
    margin-bottom: 25px;
    text-transform: capitalize;
    padding: 20px;
    height: fit-content;
}

p {
    padding: 20px;
    margin: 10px;
    font-size: 20px;
    letter-spacing: 2px;
    color: $text-color;
    background-color: $dark-background;
    border-radius: 10px;
    
}

.image {
    border-radius: 10px;
    display: flex;
    justify-content: center;
    width: auto;
    
}

@media screen and (max-width:$medium) {
    main{
        display: flex;
        flex-direction: row;
        
    }
    .image{
        display: flexbox;
    }
    .about-text{
        display: block;
        justify-content: center;
    }
    
}
```

### Passions page
For this page I wanted to add my hobbies or interests. I added the elements and wanted to display it in an easy to read manner. I made sure that the footer was close so that the user can click on the social media links to follow me for further content. Please see HTML code:
```html
    <main>

        <article>
            <section>
                <img class="service-img" src="../styles/images/photography.jpg" alt="Photography"
            </section>
            <section>
                <h3>Photography</h3>
                <h5>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste laudantium quasi doloremque a, non odio dolorem optio repellat at impedit 
                    recusandae? Voluptate repellendus quidem nemo voluptatum iste placeat ullam! Nobis.</h5>
            </section>
        </article>

        <article>
            <section>
                <img class="service-img" src="../styles/images/mixology.jpg" alt="Mixology"
            </section>
            <section>
                <h3>Mixology</h3>
                <h5>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste laudantium quasi doloremque a, non odio dolorem optio repellat at impedit 
                    recusandae? Voluptate repellendus quidem nemo voluptatum iste placeat ullam! Nobis.</h5>
            </section>
        </article>

        <article>
            <section>
                <img class="service-img" src="../styles/images/progamming.jpg" alt="Progamming"
            </section>
            <section>
                <h3>Programming</h3>
                <h5>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste laudantium quasi doloremque a, non odio dolorem optio repellat at impedit 
                    recusandae? Voluptate repellendus quidem nemo voluptatum iste placeat ullam! Nobis.</h5>
            </section>
        </article>

        <article>
            <section>
                <img class="service-img" src="../styles/images/Custom-keyboard.jpg" alt="Custom Keyboard Building"
            </section>
            <section>
                <h3>Custom Keyboard Building</h3>
                <h5>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste laudantium quasi doloremque a, non odio dolorem optio repellat at impedit 
                    recusandae? Voluptate repellendus quidem nemo voluptatum iste placeat ullam! Nobis.</h5>
            </section>
        </article>
    </main>
```
Please see SCSS code
```scss
body {
    background-image: url(../images/background-wihtewlight.jpg);
    background-size: cover;
    background-position: center;
}

main {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    height: vh;

    article {
        border: 3px solid $dark-background;
        border-radius: 8px;
        overflow: hidden;
        margin: 20px 0px;
        background-color: $primary-color;
        padding: 16px;
        text-align: center;
        

        section {
            .service-img {
                width: 350px;
                border-radius: 16px;
            }
            }
        }
    }

    @media screen and (max-width:$medium) {
        main{
            display: flex;
            flex-direction: row;
            
        }
        .image{
            display: flexbox;
        }
        .about-text{
            display: block;
            justify-content: center;
        }
        
    }
```

### Experience page
For the experience page I wanted to add the elements of the apps that Im working on but at the same time I wanted to add a link to my CV for more details of my experience.

To add responsiveness to my experience page I wanted to add some layers over the projects that I have worked on. So that when the user hovers over the individual projects they would be able to see a title of what project it is and also a simple description of the project. I also added a link for each one so it links to each of the projects (please note the link doesn't lead to anywhere). 

I have also added a link to view my CV. I added some animation to the link so that it is responsive when the user hovers over the button. When the user clicks on the button they will be able to download my CV (Example CV added in this case).

Please see HTML code below:
```html
    <div id="Portfolio">
        <div class="container">
            <h1 class="My Experience">
                <div class="work-list">
                    <div class="work">
                        <img src="../styles/images/workimage1.jpg">
                        <div class="layer">
                            <h3>Social Media App</h3>
                            <p>Lorem ipsum dolor sit amet consectetur.</p>
                            <a href="#"><i class="fa-solid fa-up-right-from-square"></i></a>
                        </div>
                    </div>
                    <div class="work">
                        <img src="../styles/images/workimage5.jpg">
                        <div class="layer">
                            <h3>Online Shopping App</h3>
                            <p>Lorem ipsum dolor sit amet consectetur.</p>
                            <a href="#"><i class="fa-solid fa-up-right-from-square"></i></a>
                        </div>
                    </div>
                    <div class="work">
                        <img src="../styles/images/workimage3.jpg">
                        <div class="layer">
                            <h3>Productivity App</h3>
                            <p>Lorem ipsum dolor sit amet consectetur.</p>
                            <a href="#"><i class="fa-solid fa-up-right-from-square"></i></a>
                        </div>
                    </div>
                    <div class="work">
                        <img src="../styles/images/workimage6.jpg">
                        <div class="layer">
                            <h3>Fitness App</h3>
                            <p>Lorem ipsum dolor sit amet consectetur.</p>
                            <a href="#"><i class="fa-solid fa-up-right-from-square"></i></a>
                        </div>
                    </div>
                    <div class="work">
                        <img src="../styles/images/workimage8.jpg">
                        <div class="layer">
                            <h3>Travelling App</h3>
                            <p>Lorem ipsum dolor sit amet consectetur.</p>
                            <a href="#"><i class="fa-solid fa-up-right-from-square"></i></a>
                        </div>
                    </div>
                    <div class="work">
                        <img src="../styles/images/workimage9.jpg">
                        <div class="layer">
                            <h3>Cooking App</h3>
                            <p>Lorem ipsum dolor sit amet consectetur.</p>
                            <a href="#"><i class="fa-solid fa-up-right-from-square"></i></a>
                        </div>
                    </div>
            </div>
            <a href="../Resume Lorem Ipsum.pdf" download class="btn">Check out my CV</a>
        </h1>
    </div>
</div>
```
Please see SCSS code
```scss
body {
    background-image: url(../images/background-wihtewlight.jpg);
    background-size: cover;
    background-position: center;
}

#portfolio{
    padding: 50px 0;
}

.container{
    margin-top: 100px;
}

.work-list{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 40px;
    margin-top: 50px;
    justify-content: space-between;
    margin: 20px;
}

.work{
    border-radius: 10px;
    position: relative;
    overflow: hidden;
}
.work img{
    width: 100%;
    border-radius: 10px;
    display: block;
    transition: transform 0.5s;
}

.layer{
    width: 100%;
    height: 0;
    background: linear-gradient(rgba(0,0,0,0.6), $primary-color);
    border-radius: 10px;
    position: absolute;
    left: 0;
    bottom: 0;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 0 40px;
    text-align: center;
    transition: height 0.5s;
}

.layer h3{
    font-weight: 700;
    margin-bottom: 20px;
    font-size: 20px;
    color: $primary-color;
}

.layer p{
    font-size: 18px;
}

.layer a{
    margin-top: 20px;
    color: $dark-background;
    text-decoration: none;
    font-size: 18px;
    line-height: 60px;
    background: $secondary-color;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    text-align: center;
}

.work:hover img{
    transform: scale(1.1);
}

.work:hover .layer{
    height:100%

}

.btn{
    display: block;
    margin: 50px auto;
    width: fit-content;
    border: 1px solid $dark-background;
    border-radius: 6px;
    padding: 14px 50px;
    text-decoration: none;
    color: $dark-background;
    transition: background 0.5s;
    font-weight: 700;
    background: $primary-color;
}

.btn:hover{
    background: $dark-background;
    color: $primary-color;
}

@media screen and (max-width:$medium) {
    main{
        display: flex;
        flex-direction: row;
        
    }
    .image{
        display: flexbox;
    }
    .about-text{
        display: block;
        justify-content: center;
    }
    
}
```

### Contact Page
For the contact page I wanted to add certain elements to the page so that the user can contact me with ease. I added the forms to input name, email and message. I have added another button for the user to download my CV if required. Lastly I have added a submit button so that the user can send their enquiry to me. I added measures to ensure that the fields need to be filled in before submitting the enquiry.

Please see HTML code:
```html
    <div id="contact">
        <div class="container">
            <div class="row">
                <div class="contact-left">
                    <h1 class="sub-heading">Contact Me</h1>
                    <p><i class="fa-solid fa-envelope"></i>contact@gmail.com.au</p>
                    <p><i class="fa-solid fa-mobile-screen"></i>0404 123 456</p>
                    <a href="../Resume Lorem Ipsum.pdf" download class="btn btn2">Download CV</a>
                </div>
                <div class="contact-right">
                    <form>
                        <input type="text" name="Name" placeholder="Your Name" required>
                        <input type="email" name="email" placeholder="Your Email" required>
                        <textarea name="Message" rows="6" placeholder="Your Message"></textarea>
                        <button type="submit" class="btn btn2">Submit your enquiry</button>
                    </form>
                </div>
            </div>
        </div>
    </div>
```
Please see SCSS code
```scss
body {
    background-image: url(../images/background-wihtewlight.jpg);
    background-size: cover;
    background-position: center;
}


.contact-left{
    flex-basis: 35%;
    color: $dark-background;
    margin-left: 50px;
    margin-top: 50px;
    padding: 5px;

    p{
        padding: 5px;
    }
}


.contact-right{
    flex-basis: 60%;
    margin-left: 50px;
}

.contact-left p{
    margin-top: 30px;
}

.contact-left i{
    color: $dark-background;
    margin-right: 15px;
    font-size: 25px;
}
.contact-right form{
    width: 70%;
    display: block;
}

.btn{
    display: inline-block;
    margin: 50px auto;
    width: fit-content;
    border: 1px solid $dark-background;
    border-radius: 6px;
    padding: 14px 50px;
    text-decoration: none;
    color: $primary-color;
    transition: background 0.5s;
    font-weight: 700;
    background: $dark-background;
}

.btn:hover{
    background: $primary-color;
    color: $dark-background;
}

form{
    display: inline-block;
    justify-content: center;
}

form input, form textarea{
    width: 100%;
    border: 0;
    outline: none;
    background: $secondary-color;
    padding: 15px;
    margin: 15px 0;
    color: $dark-background;
    font-size: 18px;
    border-radius: 6px;
}

form .btn.btn2{
    padding: 14px 60px;
    font-size: 18px;
    margin-top: 20px;
    cursor: pointer;

}

@media screen and (max-width:$medium) {
    main{
        display: flex;
        flex-direction: row;
        
    }
    .image{
        display: flexbox;
    }
    .about-text{
        display: block;
        justify-content: center;
    }
    
}
```

