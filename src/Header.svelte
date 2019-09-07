<style type="text/css">
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .header-container{
        display:flex;
        /*margin:auto;*/
        margin-left: 5%;
        margin-right: 5%;
        justify-content: space-between;
    }

    .title-button{
        color:black;
        text-transform: uppercase;
        font-size: 4vw;
        background-color: Transparent;
        background-repeat: no-repeat;
        border: none;
        cursor:pointer;
        overflow: hidden;
        outline:none;
    }

    .title-button:hover{
        color:gray;
        text-transform: uppercase;
        font-size: 4vw;
        background-color: Transparent;
        background-repeat: no-repeat;
        border: none;
        cursor:pointer;
        overflow: hidden;
        outline:none;
    }

    .menu-container{
        display: flex;
        /*margin-left: auto;*/
        justify-content: flex-end;
    }

    .menu-buttons{
        padding: 15px;
        background-color: Transparent;
        background-repeat:no-repeat;
        border: none;
        cursor:pointer;
        overflow: hidden;
        outline:none;
    }
</style>

<script>
    export let selected = 'home';

    //function menuButtonHandler(name){

    //}

</script>

<div class="header-container">
    <button class="title-button">Kaelan Moffett-Steinke</button>
    <div class="menu-container">
        <button class="menu-buttons">Portfolio</button>
        <button class="menu-buttons">Contact</button>
        <button class="menu-buttons">Other</button>
    </div>
</div>