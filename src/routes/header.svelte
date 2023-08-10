<div id="header">
    <h1 class="line">GRAHAM'S GREAT GULP</h1>
    <h1 id="and">&</h1>
    <h1 class="line">CARD CHAMPIONSHIP</h1>
</div>

<style>
    h1 {
        text-align: left;
        font-style: normal;
        margin: 0;
        font-size: 4em;
    }

    #header {
        display: grid;
        grid-template-columns: 80% 20%;
    }

    .line {
        font-size: 5.5em;
    }

    #and {
        grid-column: 2;
        grid-row: 1 / span 2;
        
        font-size: 10em;
        font-family: 'Roboto Mono', monospace;
    }

    @media only screen and (max-width: 1000px) {
        .line {
            font-size: 4.5em;
        }
    }

    @media only screen and (max-width: 800px) {
        .line {
            font-size: 4em;
        }
    }

    @media only screen and (max-width: 500px) {
        #header {
            display: block;
        }

        .line {
            font-size: 3em;
            text-align: center;
        }

        #and {
            text-align: center;
            font-size: 4em;
        }
    }
</style>