// Charger les dépenses sauvegardées
let expenses = JSON.parse(localStorage.getItem("expenses")) || [];

// Sauvegarder les dépenses dans le navigateur
function saveExpenses() {
    localStorage.setItem("expenses", JSON.stringify(expenses));
}

// Ajouter une dépense
function addExpense(name, amount) {
    const expense = {
        id: Date.now(),
        name: name,
        amount: Number(amount)
    };

    expenses.push(expense);
    saveExpenses();
}

// Supprimer une dépense
function deleteExpense(id) {
    expenses = expenses.filter(expense => expense.id !== id);
    saveExpenses();
}
