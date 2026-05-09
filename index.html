/* =========================
   TRIP CONTRIBUTION MANAGER
========================= */

/* -------------------------
   LOCAL STORAGE KEYS
------------------------- */

const MEMBER_KEY = "trip_members";
const EXPENSE_KEY = "trip_expenses";

/* -------------------------
   DEFAULT MEMBERS
------------------------- */

let members =
  JSON.parse(localStorage.getItem(MEMBER_KEY)) || [
    "Shivang",
    "Rahul",
    "Vivek",
  ];

let expenses =
  JSON.parse(localStorage.getItem(EXPENSE_KEY)) || [];

/* -------------------------
   ELEMENTS
------------------------- */

const expenseModal = document.getElementById("expenseModal");
const openExpenseModal = document.getElementById("openExpenseModal");
const closeExpenseModal = document.getElementById("closeExpenseModal");

const paidBy = document.getElementById("paidBy");
const paidForArea = document.getElementById("paidForArea");

const expenseList = document.getElementById("expenseList");

const saveExpenseBtn = document.getElementById("saveExpenseBtn");

const toast = document.getElementById("toast");

/* -------------------------
   OPEN MODAL
------------------------- */

openExpenseModal.addEventListener("click", () => {
  expenseModal.style.display = "flex";
});

closeExpenseModal.addEventListener("click", () => {
  expenseModal.style.display = "none";
});

/* -------------------------
   TOAST
------------------------- */

function showToast(message) {
  toast.innerText = message;
  toast.style.display = "block";

  setTimeout(() => {
    toast.style.display = "none";
  }, 2000);
}

/* -------------------------
   RENDER MEMBER DROPDOWN
------------------------- */

function renderMembers() {

  paidBy.innerHTML = "";

  const memberFilter = document.getElementById("memberFilter");

  memberFilter.innerHTML =
    `<option value="">All Members</option>`;

  members.forEach((member) => {

    const option = document.createElement("option");
    option.value = member;
    option.innerText = member;

    paidBy.appendChild(option);

    const filterOption = option.cloneNode(true);
    memberFilter.appendChild(filterOption);

  });

  renderPaidForChips();

  renderMemberList();

  document.getElementById("memberCount").innerText =
    members.length;
}

/* -------------------------
   MEMBER CHIPS
------------------------- */

function renderPaidForChips() {

  paidForArea.innerHTML = "";

  members.forEach((member) => {

    const chip = document.createElement("div");

    chip.className = "member-chip active";
    chip.innerText = member;

    chip.dataset.member = member;

    chip.addEventListener("click", () => {
      chip.classList.toggle("active");
    });

    paidForArea.appendChild(chip);

  });

}

/* -------------------------
   SAVE EXPENSE
------------------------- */

saveExpenseBtn.addEventListener("click", () => {

  const amount =
    Number(document.getElementById("amount").value);

  const expenseName =
    document.getElementById("expenseName").value;

  const category =
    document.getElementById("category").value;

  const paidByValue =
    paidBy.value;

  const notes =
    document.getElementById("notes").value;

  const dateTime =
    document.getElementById("dateTime").value;

  const selectedMembers = [];

  document
    .querySelectorAll(".member-chip.active")
    .forEach((chip) => {
      selectedMembers.push(chip.dataset.member);
    });

  if (
    !amount ||
    !expenseName ||
    selectedMembers.length === 0
  ) {
    showToast("Please fill all fields");
    return;
  }

  const expense = {
    id: Date.now(),
    amount,
    expenseName,
    category,
    paidBy: paidByValue,
    paidFor: selectedMembers,
    notes,
    dateTime,
  };

  expenses.unshift(expense);

  saveData();

  renderExpenses();

  renderDashboard();

  renderSettlement();

  renderCharts();

  expenseModal.style.display = "none";

  showToast("Expense Added");

});

/* -------------------------
   SAVE LOCAL STORAGE
------------------------- */

function saveData() {

  localStorage.setItem(
    MEMBER_KEY,
    JSON.stringify(members)
  );

  localStorage.setItem(
    EXPENSE_KEY,
    JSON.stringify(expenses)
  );

}

/* -------------------------
   RENDER EXPENSES
------------------------- */

function renderExpenses() {

  expenseList.innerHTML = "";

  const search =
    document
      .getElementById("searchInput")
      .value
      .toLowerCase();

  const memberFilter =
    document.getElementById("memberFilter").value;

  const categoryFilter =
    document.getElementById("categoryFilter").value;

  let filtered = expenses.filter((expense) => {

    let matchSearch =
      expense.expenseName
        .toLowerCase()
        .includes(search);

    let matchMember =
      !memberFilter ||
      expense.paidBy === memberFilter;

    let matchCategory =
      !categoryFilter ||
      expense.category === categoryFilter;

    return (
      matchSearch &&
      matchMember &&
      matchCategory
    );

  });

  filtered.forEach((expense) => {

    const card = document.createElement("div");

    card.className = "expense-card";

    card.innerHTML = `
    
      <div class="expense-top">
        <div>
          <h3>${expense.expenseName}</h3>
          <p>${expense.category}</p>
        </div>

        <h2>₹${expense.amount}</h2>
      </div>

      <p><b>Paid By:</b> ${expense.paidBy}</p>

      <p><b>Paid For:</b>
      ${expense.paidFor.join(", ")}
      </p>

      <p><b>Notes:</b> ${expense.notes || "-"}</p>

      <div class="expense-actions">

        <button onclick="deleteExpense(${expense.id})">
          Delete
        </button>

      </div>
    
    `;

    expenseList.appendChild(card);

  });

}

/* -------------------------
   DELETE EXPENSE
------------------------- */

function deleteExpense(id) {

  if (!confirm("Delete this expense?")) return;

  expenses =
    expenses.filter((e) => e.id !== id);

  saveData();

  renderExpenses();

  renderDashboard();

  renderSettlement();

  renderCharts();

  showToast("Expense Deleted");

}

/* -------------------------
   DASHBOARD
------------------------- */

function renderDashboard() {

  let total = 0;

  let spender = {};

  expenses.forEach((expense) => {

    total += expense.amount;

    spender[expense.paidBy] =
      (spender[expense.paidBy] || 0) +
      expense.amount;

  });

  document.getElementById(
    "totalExpense"
  ).innerText = `₹${total}`;

  let highest = "-";
  let highestAmount = 0;

  Object.keys(spender).forEach((member) => {

    if (spender[member] > highestAmount) {

      highestAmount = spender[member];
      highest = member;

    }

  });

  document.getElementById(
    "highestSpender"
  ).innerText = highest;

  const recentExpenses =
    document.getElementById("recentExpenses");

  recentExpenses.innerHTML = "";

  expenses.slice(0, 4).forEach((expense) => {

    const div = document.createElement("div");

    div.className = "expense-card";

    div.innerHTML = `
      <h3>${expense.expenseName}</h3>
      <p>₹${expense.amount}</p>
    `;

    recentExpenses.appendChild(div);

  });

}

/* -------------------------
   SETTLEMENT LOGIC
------------------------- */

function renderSettlement() {

  const settlementList =
    document.getElementById("settlementList");

  settlementList.innerHTML = "";

  let balances = {};

  members.forEach((m) => {
    balances[m] = 0;
  });

  expenses.forEach((expense) => {

    const split =
      expense.amount /
      expense.paidFor.length;

    balances[expense.paidBy] += expense.amount;

    expense.paidFor.forEach((member) => {
      balances[member] -= split;
    });

  });

  let creditors = [];
  let debtors = [];

  Object.keys(balances).forEach((member) => {

    let value =
      Number(balances[member].toFixed(2));

    if (value > 0) {
      creditors.push({
        member,
        amount: value,
      });
    }

    if (value < 0) {
      debtors.push({
        member,
        amount: Math.abs(value),
      });
    }

  });

  let settlements = [];

  debtors.forEach((debtor) => {

    creditors.forEach((creditor) => {

      if (
        debtor.amount > 0 &&
        creditor.amount > 0
      ) {

        let payAmount =
          Math.min(
            debtor.amount,
            creditor.amount
          );

        settlements.push(
          `${debtor.member} pays ${creditor.member} ₹${payAmount.toFixed(0)}`
        );

        debtor.amount -= payAmount;
        creditor.amount -= payAmount;

      }

    });

  });

  document.getElementById(
    "settlementCount"
  ).innerText = settlements.length;

  if (settlements.length === 0) {

    settlementList.innerHTML =
      "<p>All settled 🎉</p>";

    return;

  }

  settlements.forEach((text) => {

    const div = document.createElement("div");

    div.className = "expense-card";

    div.innerHTML = `
      <h3>${text}</h3>

      <button onclick="shareWhatsApp('${text}')">
        Share WhatsApp
      </button>
    `;

    settlementList.appendChild(div);

  });

}

/* -------------------------
   WHATSAPP SHARE
------------------------- */

function shareWhatsApp(text) {

  const url =
    `https://wa.me/?text=${encodeURIComponent(text)}`;

  window.open(url, "_blank");

}

/* -------------------------
   CHARTS
------------------------- */

let pieChart;
let barChart;
let categoryChart;

function renderCharts() {

  let contribution = {};

  let category = {};

  members.forEach((m) => {
    contribution[m] = 0;
  });

  expenses.forEach((expense) => {

    contribution[expense.paidBy] += expense.amount;

    category[expense.category] =
      (category[expense.category] || 0) +
      expense.amount;

  });

  if (pieChart) pieChart.destroy();

  pieChart = new Chart(
    document.getElementById("pieChart"),
    {
      type: "pie",

      data: {
        labels: Object.keys(contribution),

        datasets: [{
          data: Object.values(contribution),
        }],
      },
    }
  );

  if (barChart) barChart.destroy();

  barChart = new Chart(
    document.getElementById("barChart"),
    {
      type: "bar",

      data: {
        labels: Object.keys(contribution),

        datasets: [{
          data: Object.values(contribution),
        }],
      },
    }
  );

  if (categoryChart) categoryChart.destroy();

  categoryChart = new Chart(
    document.getElementById("categoryChart"),
    {
      type: "doughnut",

      data: {
        labels: Object.keys(category),

        datasets: [{
          data: Object.values(category),
        }],
      },
    }
  );

}

/* -------------------------
   MEMBER LIST
------------------------- */

function renderMemberList() {

  const memberList =
    document.getElementById("memberList");

  memberList.innerHTML = "";

  members.forEach((member, index) => {

    const div = document.createElement("div");

    div.className = "member-item";

    div.innerHTML = `
    
      <h3>${member}</h3>

      <div class="member-actions">

        <button onclick="editMember(${index})">
          Edit
        </button>

        <button onclick="removeMember(${index})">
          Remove
        </button>

      </div>
    
    `;

    memberList.appendChild(div);

  });

}

/* -------------------------
   ADD MEMBER
------------------------- */

document
  .getElementById("addMemberBtn")
  .addEventListener("click", () => {

    const name =
      prompt("Enter member name");

    if (!name) return;

    members.push(name);

    saveData();

    renderMembers();

    showToast("Member Added");

  });

/* -------------------------
   REMOVE MEMBER
------------------------- */

function removeMember(index) {

  if (!confirm("Remove member?")) return;

  members.splice(index, 1);

  saveData();

  renderMembers();

}

/* -------------------------
   EDIT MEMBER
------------------------- */

function editMember(index) {

  const newName =
    prompt(
      "Edit member",
      members[index]
    );

  if (!newName) return;

  members[index] = newName;

  saveData();

  renderMembers();

}

/* -------------------------
   SEARCH FILTERS
------------------------- */

document
  .getElementById("searchInput")
  .addEventListener("input", renderExpenses);

document
  .getElementById("memberFilter")
  .addEventListener("change", renderExpenses);

document
  .getElementById("categoryFilter")
  .addEventListener("change", renderExpenses);

/* -------------------------
   NAVIGATION
------------------------- */

document
  .querySelectorAll(".nav-btn")
  .forEach((button) => {

    button.addEventListener("click", () => {

      document
        .querySelectorAll(".nav-btn")
        .forEach((btn) => {
          btn.classList.remove("active-nav");
        });

      button.classList.add("active-nav");

      document
        .querySelectorAll(".page")
        .forEach((page) => {
          page.classList.remove("active-page");
        });

      document
        .getElementById(button.dataset.page)
        .classList.add("active-page");

    });

  });

/* -------------------------
   DARK MODE
------------------------- */

document
  .getElementById("themeBtn")
  .addEventListener("click", () => {

    document.body.classList.toggle("light");

  });

/* -------------------------
   EXPORT EXCEL
------------------------- */

document
  .getElementById("excelBtn")
  .addEventListener("click", () => {

    const worksheet =
      XLSX.utils.json_to_sheet(expenses);

    const workbook =
      XLSX.utils.book_new();

    XLSX.utils.book_append_sheet(
      workbook,
      worksheet,
      "Expenses"
    );

    XLSX.writeFile(
      workbook,
      "trip-expenses.xlsx"
    );

  });

/* -------------------------
   EXPORT PDF
------------------------- */

document
  .getElementById("pdfBtn")
  .addEventListener("click", () => {

    const { jsPDF } = window.jspdf;

    const doc = new jsPDF();

    doc.text(
      "Trip Expense Summary",
      20,
      20
    );

    let y = 40;

    expenses.forEach((expense) => {

      doc.text(
        `${expense.expenseName} - ₹${expense.amount}`,
        20,
        y
      );

      y += 10;

    });

    doc.save("trip-summary.pdf");

  });

/* -------------------------
   SHARE SUMMARY
------------------------- */

document
  .getElementById("shareBtn")
  .addEventListener("click", async () => {

    let text = "Trip Expense Summary\n\n";

    expenses.forEach((expense) => {

      text +=
        `${expense.expenseName} - ₹${expense.amount}\n`;

    });

    if (navigator.share) {

      navigator.share({
        title: "Trip Summary",
        text,
      });

    } else {

      alert(text);

    }

  });

/* -------------------------
   INITIALIZE
------------------------- */

renderMembers();

renderExpenses();

renderDashboard();

renderSettlement();

renderCharts();
