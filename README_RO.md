# Examen 2: Cantina Centrului Județean de Pregătire

## Reguli de Predare (Citește Primul)

> **Doar lucrările trimise prin Git vor fi evaluate.** Soluțiile trimise prin email, chat, screenshot sau orice alt canal nu vor fi acceptate.

1. **Creează un branch din `main`.** Deschide un branch curat numit exact:
   ```
   exam/firstname_lastname
   ```
   Exemplu: `exam/ion_popescu`
2. **Lucrează doar pe branch-ul tău.** Nu face push direct pe `main`.
3. **Deschide un Pull Request către `main` când ai terminat.** Titlul PR-ului trebuie să fie exact:
   ```
   EXAM - Prenume Nume
   ```
   Exemplu: `EXAM - Ion Popescu`
4. **Fă commit și push înainte de expirarea timpului.** Un PR care nu este deschis până la termenul limită nu va fi evaluat.

## Povestea
Un centru județean de pregătire găzduiește un mare atelier de servicii publice, iar cantina trebuie să servească personalul rapid și corect în timpul pauzei de prânz. Codul tău va ajuta cantina să înregistreze comenzile, să calculeze totalurile și să pregătească mesele în ordinea corectă a cozii.

Tot ce ai nevoie se află în `main.py`.

## Formatul Examenului
- Timp alocat: 90 - 120 minute
- Fișierul principal: `main.py`
- Focus: crearea obiectelor, adăugarea în liste, `isinstance`, bucle, logica de coadă FIFO, actualizări simple de dicționare

## Sarcini Principale
1. Completează `Order.add_item()` astfel încât articolele din meniu să fie stocate în comandă.
2. Completează `Order.calculate_subtotal()` prin însumarea prețurilor articolelor.
3. Completează `Order.calculate_total()`:
   - mesele (Meal) primesc 9% TVA
   - băuturile (Drink) primesc 19% TVA
4. Completează `Kitchen.add_order()` astfel încât comenzile să se adauge la sfârșitul cozii.
5. Completează `Kitchen.prepare_next_order()` astfel încât:
   - să elimine cea mai veche comandă (FIFO)
   - să reducă inventarul pentru fiecare ingredient din fiecare masă
   - să printeze un avertisment dacă un ingredient scade sub `0`

## Ce Este Deja Oferit
- Clasele de start
- Exemple de articole de meniu
- Un inventar de start
- O listă de comportamente de testat

## Exemplu de Date de Intrare și Ieșire Așteptată

**Intrare (Meniu și Inventar):**
- Inventar: `{"tomatoes": 5, "bread": 2}`
- Masă: `Salata de Rosii` (Preț: `10`, Ingrediente: `["tomatoes", "tomatoes"]`)
- Băutură: `Apa` (Preț: `5`, Servit Rece: `True`)

**Acțiune:**
```python
order = Order("Masa 1")
order.add_item(Meal)
order.add_item(Drink)

kitchen = Kitchen(Inventar)
kitchen.add_order(order)
kitchen.prepare_next_order()
```

**Rezultate Așteptate:**
- `calculate_subtotal()` ar trebui să returneze `15` (10 + 5).
- `calculate_total()` ar trebui să returneze `16.85` (10 * 1.09 + 5 * 1.19).
- După `prepare_next_order()`, inventarul bucătăriei pentru `"tomatoes"` ar trebui să fie `3` (5 - 2).

## Sarcina Opțională
La finalul fișierului `main.py`, completează `count_item_names(orders)`.

Acest bonus îți cere să construiești un dicționar care contorizează de câte ori apare numele fiecărui articol din meniu într-o mulțime de comenzi.

## Rulare
```bash
python main.py
```