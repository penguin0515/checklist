# 測試 Checklist（可互動 + 自動更新）

<input type="checkbox" class="task" data-id="t1"> A 任務<br>
<input type="checkbox" class="task" data-id="t2"> B 任務<br>
<input type="checkbox" class="task" data-id="t3"> C 任務<br>

<p id="progress">完成進度：0 / 3（0%）</p>

<script>
document.addEventListener("DOMContentLoaded", function () {
    const tasks = document.querySelectorAll('.task');
    const progress = document.getElementById('progress');

    function update() {
        let done = 0;
        tasks.forEach(t => { if (t.checked) done++; });
        const percent = Math.round((done / tasks.length) * 100);
        progress.innerText = `完成進度：${done} / ${tasks.length}（${percent}%）`;
    }

    tasks.forEach(t => t.addEventListener("change", update));

    update();  // 初始化
});
</script>
