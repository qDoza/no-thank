addEventListener("click", () => {
      if (armedDay === day.id) {
        days = days.filter(d => d.id !== day.id);
        armedDay = null; save(); render();
      } else {
        armedDay = day.id;
        clearTimeout(armedTimer);
        armedTimer = setTimeout(() => { armedDay = null; render(); }, 3000);
        render();
      }
    });
    head.appendChild(del);
    wrap.appendChild(head);

    day.items.forEach((item, idx) => {
      const row = el("div", "item" + (item.done ? " done" : ""));

      const box = el("button", "box");
      box.setAttribute("aria-label", "Отметить выполненным");
      box.setAttribute("aria-pressed", String(item.done));
      box.addEventListener("click", () => {
        item.done = !item.done;
        row.classList.toggle("done", item.done);
        box.setAttribute("aria-pressed", String(item.done));
        updateCount(); save();
      });

      const inp = el("input", "txt", { value: item.text, placeholder: "Упражнение" });
      inp.dataset.item = item.id;
      inp.addEventListener("input", () => { item.text = inp.value; save(); });
      inp.addEventListener("keydown", e => {
        if (e.key === "Enter") {
          e.preventDefault();
          const n = { id: uid(), text: "", done: false };
          day.items.splice(idx + 1, 0, n);
          save(); render(); focusItem(n.id);
        } else if (e.key === "Backspace" && inp.value === "") {
          e.preventDefault();
          day.items.splice(idx, 1);
          const prev = day.items[idx - 1];
          save(); render();
          if (prev) focusItem(prev.id, true);
        }
      });

      row.append(box, inp);
      wrap.appendChild(row);
    });

    const add = el("button", "add");
    add.innerHTML = '<span class="plus">+</span><span>Добавить упражнение</span>';
    add.addEventListener("click", () => {
      const n = { id: uid(), text: "", done: false };
      day.items.push(n);
      save(); render(); focusItem(n.id);
    });
    wrap.appendChild(add);

    app.appendChild(wrap);
  });

  if (days.length === 0) {
    const empty = el("p", "", { textContent: "Пока пусто. Нажми «Новый день», чтобы начать план." });
    empty.style.color = "var(--dim)";
    empty.style.fontSize = "18px";
    app.appendChild(empty);
  }
}

const MONTH_KEYS = ["jan", "feb", "mar", "apr", "may", "jun", "jul", "aug", "sep", "oct", "nov", "dec"];
const MONTH_LABELS = ["Jan.", "Feb.", "Mar.", "Apr.", "May", "June", "July", "Aug.", "Sept.", "Oct.", "Nov.", "Dec."];
const WEEKDAY_LABELS = ["Sun.", "Mon.", "Tue.", "Wed.", "Thu.", "Fri.", "Sat."];

// Достаёт дату из заголовка вида "Wed. Oct. 7" и возвращает следующий день
function nextDateAfter(title) {
  const m = /([a-z]{3})[a-z]*\.?\s*(\d{1,2})/i.exec(title || "");
  if (m) {
    const mi = MONTH_KEYS.indexOf(m[1].toLowerCase());
    if (mi !== -1) {
      const d = new Date(new Date().getFullYear(), mi, parseInt(m[2], 10));
      d.setDate(d.getDate() + 1);
      return d;
    }
  }
  return new Date();
}

document.getElementById("addDay").addEventListener("click", () => {
  const last = days.length ? days[days.length - 1].title : "";
  const d = nextDateAfter(last);
  const wd = WEEKDAY_LABELS[d.getDay()];
  const mo = MONTH_LABELS[d.getMonth()];
  const n = { id: uid(), title: wd + " " + mo + " " + d.getDate(), items: [{ id: uid(), text: "", done: false }] };
  days.push(n);
  save(); render();
  focusItem(n.items[0].id);
  window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
});

document.getElementById("resetChecks").addEventListener("click", () => {
  days.forEach(d => d.items.forEach(i => i.done = false));
  save(); render();
});

if ("serviceWorker" in navigator) {
  navigator.serviceWorker.register("./sw.js").catch(() => {});
}

load();
</script>

</body>
</html>
