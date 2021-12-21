# Ruby On rails course for beginners

## Goal of this text
This recent course introduces any newbie to the world of Ruby On Rails. But before that, he must know what Ruby On Rails is in concrete terms then the prior knowledge to have for learning Ruby on Rails

## What is Ruby on rails?
Ruby on Rails (RoR) is an open-source web development framework based on the Ruby programming language. Many people generally confuse Ruby with Ruby on Rails. Rails is a server-side framework for developing websites and web applications using Ruby, a high-level programming language.

## what are the basics to have?
Learning Ruby on Rails like any other framework requires prior knowledge of certain technologies. In the case of Ruby On Rails we will do a brief tour of the following technologies: HTML, CSS, JavaScript, Ruby, Github etc.

### HTML
HTML stands for "HyperText Markup Language". It is a language used to compose web pages. We are talking about markup language and not programming language, because the goal of HTML is to frame the different elements present in a page (images, titles, paragraphs ...) by tags to allow them to be put in secondarily (via a stylesheet) and to give them meaning.
*Thus we may come up against certain terms when using this technology, such as: Balises, Attributs*

***Balises Exemple:*** Une balise est formée en encadrant le nom de l'élément avec les symboles < et > 
```
<H1>L'estuaire de Seine</H1>
Lieu magique, rencontre du fleuve et de la mer, un environnement unique,
l'estuaire de Seine est aussi un lieu de communication important... 
```
Ce code produit l'affichage suivant dans un navigateur graphique :


># L'estuaire de Seine
>Lieu magique, rencontre du fleuve et de la mer, un environnement unique, l'estuaire de Seine est aussi un lieu de communication important... 



***Attributs Exemple:*** The syntax is simple: "attribute name" = "attribute value".
```
<IMG src="bateau01.jpg" alt="Un bateau">
```
*Note 1: The IMG element does not need an end tag* .

*Note 2: the **alt** attribute of the IMG element is essential to build accessible pages* .



***Skeleton of an HTML document***
```
<!DOCTYPE HTML>
<HTML>
  <HEAD>
    <TITLE>Bienvenue dans l'estuaire de Seine</TITLE>
  </HEAD>
  <BODY>
    <H1>L'estuaire de Seine</H1>
    <P>Lieu magique, rencontre du fleuve et de la mer, un environnement unique,
    l'estuaire de Seine est aussi un lieu de communication important... 
  </BODY>
</HTML>
```



### CSS

CSS (Cascading Style Sheets) allows you to create clean looking web pages.
Thanks to CSS, you can control exactly how each HTML element is displayed in the browser and thus present your documents with the formatting of your choice.

***For example "I want the main title of my page to be displayed in red in large print."***

*In the following code, a basic CSS rule does this formatting:*
```
h1 {
  color: red;
  font-size: 5em;
}

```

For more information here [HTLM AND CSS](https://www.pierre-giraud.com/html-css-apprendre-coder-cours/)


### JavaScript
JavaScript is a programming language that allows you to implement complex mechanisms on a web page. Whenever a web page does more than just display static content - display updated content at set times, interactive maps, 2D / 3D animations, scrolling video menus, or the like, JavaScript has good results. chances of being involved. This is the third layer of standard web technologies, the first two (HTML and CSS) being presented previously.

***Applying a click action to our H1 title***
```
let para = document.querySelector('h1');

para.addEventListener('click', updateName);

function updateName() {
  let name = prompt('Changer le titre H1');
  para.textContent = name;
}

```

For more information here [JavaScript](https://www.pierre-giraud.com/javascript-apprendre-coder-cours/)

### Ruby
Ruby is a purely object-oriented language, but it is also suitable for procedural and functional programming styles. ... Ruby is an interpreted rather than a compiled language. You can call it a scripting language, an object oriented language, a refreshing language.
*Two actions are common in Ruby like any other language it is about entering and displaying data: gets and puts*


***Ruby code example***
```
require "date"
     
     print "Bonjour.\n Quel est ton nom ? "
     pren = gets.chomp()
     pren = "Bel(le) inconnu(e)" if pren.length()==0
     puts "Le " + Time.now.strftime(" %d/%m/%Y vers %H h %M") + " au revoir, " + pren.upcase() + ". "

```

For more information here [Ruby](https://zestedesavoir.com/tutoriels/634/une-introduction-a-ruby/)


### Github
GitHub is a website and cloud service that helps developers store and manage their code, as well as track and control changes to it.

*Some essential commands on Github:*
![versionner](https://user-images.githubusercontent.com/65257248/146934940-208cb197-c7bb-4056-8aa9-d0f9eb111ca6.png)

Register here [Github](https://github.com)
