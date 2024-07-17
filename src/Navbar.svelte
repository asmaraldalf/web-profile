<script>
    
    function scrollToSection(sectionId) {
        const section = document.getElementById(sectionId);
        if (section) {
            section.scrollIntoView({ behavior: 'smooth' });
        }
    }

    function handleKeyDown(event) {
        if (event.key === 'Enter') {
            const sectionId = event.target.getAttribute('href').substring(1); // Get sectionId from href
            scrollToSection(sectionId);
        }
    }
</script>

<nav class="navbar">
    <ul class="navbar-nav">
        <li><a href="#home" on:click|preventDefault="{() => scrollToSection('home')}" on:keydown="{handleKeyDown}">Home</a></li>
        <li><a href="#about" on:click|preventDefault="{() => scrollToSection('about')}" on:keydown="{handleKeyDown}">About</a></li>
        <li><a href="#project" on:click|preventDefault="{() => scrollToSection('projects')}" on:keydown="{handleKeyDown}">Projects</a></li>
        <li><a href="#contact" on:click|preventDefault="{() => scrollToSection('contact')}" on:keydown="{handleKeyDown}">Contact</a></li>
    </ul>
</nav>

<style>
    .navbar {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        background-color: #333;
        padding: 10px;
        z-index: 1000; /* Ensure it appears above other content */
    }

    .navbar-nav {
        list-style-type: none;
        padding: 0;
        display: flex;
        justify-content: flex-end; /* Align items to the right */
    }

    .navbar-nav li {
        margin-right: 15px;
    }

    .navbar-nav li a {
        color: #fff;
        text-decoration: none;
        font-weight: bold;
        cursor: pointer; /* Ensure the cursor changes to indicate clickability */
        padding: 8px 15px; /* Adjust padding for clickable area */
    }
</style>