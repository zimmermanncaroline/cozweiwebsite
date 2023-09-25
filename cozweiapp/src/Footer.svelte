<script>
  let showData = false;
  let showContact = false;
  let showImprint = false;

  const toggleData = () => {
    showData = !showData;
    showContact = false;
    showImprint = false;
  }

  const toggleContact = () => {
    showContact = !showContact;
    showData = false;
    showImprint = false;
  }

  const toggleImprint = () => {
    showImprint = !showImprint;
    showData = false;
    showContact = false;
  }
</script>

<div id="footer">
    <ul class="justify-content-center">
        <li>
          <a href="#footer" on:click={toggleContact}>Kontakt</a>
        </li>
        <li>
          <a href="#footer" on:click={toggleImprint}>Impressum</a>
        </li>
        <li>
          <a href="#footer" on:click={toggleData}>Datenschutz</a>
        </li>
      </ul>


{#if showData}
<div class="footer-container">
  <div class="data">
<p><b>Datenschutz</b></p>
<p>Consetetur sadipscing elitr, 
  sed diam nonumy eirmod tempor invidunt ut labore et dolore 
  magna aliquyam erat, sed diam voluptua. At vero eos et 
  accusam et justo duo dolores et ea rebum. Stet clita kasd 
  gubergren, no sea takimata sanctus est Lorem ipsum dolor 
  sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing 
  elitr, sed diam nonumy eirmod tempor invidunt ut labore et 
  dolore magna aliquyam erat, sed diam voluptua. At vero eos 
  et accusam et justo duo dolores et ea rebum. Stet clita kasd 
  gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
</div>
</div>
{/if}
{#if showContact}
<div class="footer-container">
  <div class="data">
<p><b>Kontakt</b></p>
<p>Caroline Zimmermann</p>
<p>Musterstraße 45, 20100 Hamburg</p>
<p>mobil: 0049177 777 777 77</p>
<p>email: czimmermann@czimmermann.de</p>
</div>
</div>
{/if}
{#if showImprint}
<div class="footer-container">
  <div class="data">
<p><b>Impressum</b></p>
<p>
  Social Media Icons "Freeuse by "Flaticon"
</p>
<p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, 
  sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat.</p> 
<p>sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.
  Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. 
  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor 
  invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. </p>
  <p>At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren.</p>
</div>
</div>
{/if}
</div>

<style>
    #footer {
        background-color: #80BD9E;
        color: black;
        padding: 2%
    }
    ul li {
      display: inline;
      padding: 2%;
    }

    ul li a {
      color: black;
    }

    ul li a:active, ul li a:focus {
      text-decoration: underline!important;;
    }

    p {
      font-size: smaller;
      margin-bottom: 0;
    }
    .footer-container {
      height: 200px;
      overflow: scroll;
    }
    .data {
      max-width: 600px;
      margin: auto;
    }
</style>