<script>

</script>

<footer>
    <div class="attribution">
        Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
        Coded by <a href="https://github.com/JesusAtao96">Jesús Alejandro Atao</a>.
    </div>
</footer>

<style>
	footer {
        grid-row: 5 / 6;
        grid-column: center-start / center-end;
        
        text-align: center;
        padding: 10px 0 40px 0;
    }

    a {
        color: var(--primary);
    }

    @media only screen and (max-width: 900px) {
        footer {
            grid-row: 6 / 7;

            grid-template-columns: repeat(auto-fit, minmax(325px, 1fr));
            grid-template-rows: min-content;
        }
    }
</style>