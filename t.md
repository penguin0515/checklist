# 測試 Checklist（可互動 + 自動更新）

← 這裡加空一行！

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

    update();
});
</script>
# 📊 圖表比對（互動式）

<select id="chartSelector">
  <option value="img1">圖表 A：趨勢比較</option>
  <option value="img2">圖表 B：分類比例</option>
  <option value="img3">圖表 C：年度分析</option>
</select>

<div id="chartContainer" style="margin-top: 20px;">
  <img id="img1" src="images/chartA.png" style="width: 80%; display:block;">
  <img id="img2" src="images/chartB.png" style="width: 80%; display:none;">
  <img id="img3" src="images/chartC.png" style="width: 80%; display:none;">
</div>

<script>
document.getElementById("chartSelector").addEventListener("change", function () {
  const selected = this.value;
  ["img1", "img2", "img3"].forEach(id => {
    document.getElementById(id).style.display = (id === selected) ? "block" : "none";
  });
});
</script>
