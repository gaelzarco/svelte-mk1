<script lang='ts'>
    const mousePosition = { x: 0, y: 0 }

    function handleMousemove(event: MouseEvent) {
        mousePosition.x = event.clientX;
        mousePosition.y = event.clientY;
    }

    function handleClick() {
        alert('clicked')
    }
</script>

<section>
    <div class='mousemove' on:mousemove={handleMousemove}>
        The mouse position is {mousePosition.x}, {mousePosition.y}
    </div>

    <button class='clickonce' on:click|once={handleClick}>
        Alert Once
    </button>
</section>

<style>
    .mousemove {
        cursor: default;
        background-color: gray;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: auto;
        text-align: center;
        width: 500px;
        height: 250px;
        border-radius: 20px;
    }

    .clickonce {
        margin-top: 20px;
    }

    section {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>