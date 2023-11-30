<script>
    import PixelBar from "./PixelBar.svelte";

    let isAnswerShow = false;
    let a = 100;
    let b = 50;

    function showAnswer() {
        isAnswerShow = true;
    }
    function next() {
        isAnswerShow = false;
        a = Math.floor(Math.random() * 100 + 5);
        b = Math.floor(Math.random() * 100 + 5);
    }
</script>

<main>
    <h1>다음 빨간 부분은 몇 픽셀일까요?</h1>
    <div class="question-box">
        <div class="question">
            <PixelBar {a} {b} />
        </div>
        <div class="bellow">
        {#if !isAnswerShow}
            <button class="btn" on:click={showAnswer}>정답</button>
        {:else}
            <p>
                <span style="color: black">{a}px</span>
                <span style="color: red">{b}px</span>
            </p>
            <button class="btn" on:click={next}>다음</button>
        {/if}
        </div>
    </div>
</main>

<style>
    .btn {
        border-bottom-left-radius: 5px;
        border-bottom-right-radius: 5px;
        padding: 10px 30px;
        width: 100%;
        border: none;
        margin-top: auto;
        transition: 0.2s ease-in-out;
        background-color: #dedede;
        cursor: pointer;
    }
    .btn:hover {
        background-color: #8f8f8f;
        color: #fff;
    }
    .btn:active {
        background-color: #626262;
    }

    .bellow {
      width: 100%;
      height: 100px;
      display: flex;
      flex-direction: column;
      justify-self: end;
    }
    .bellow p {
      padding: 0;
      margin: 5px;
    }
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        width: 100%;
        height: 100%;
    }

    .question {
        height: 100%;
        padding-top: 30px;
        flex-direction: column;
        display: flex;
        align-items: center;
    }
    .question-box {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        width: 250px;
        height: 400px;
        padding: 0;
        border-radius: 5px;
        border: 1px solid #999;
        background-color: #fcfcfc;
    }
</style>
