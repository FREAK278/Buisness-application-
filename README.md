# Business Payment Calculator PWA

A mobile-first raw material purchase and supplier payment manager for OP Foods and Patra Foods.

## Included
- Firm must be selected first for every purchase entry.
- Raw material is entered per purchase and saved under that firm; the app learns material suggestions from prior entries for that firm.
- Fixed calculation rules:
  - Weight deduction = 3.5 kg per actual quintal (0.035 Q per Q)
  - Net weight = actual weight - weight deduction
  - Amount after weight deduction = net weight × rate per quintal
  - Labour = actual quintals × ₹25
  - 1% deduction = 1% of amount after labour
  - Final payable = amount after labour - 1% deduction
- Record initial amount paid and later/partial payments.
- Dashboard with custom dates and firm filters.
- Average Price dashboard with custom dates, firm/material filters, quantity-weighted purchase average and effective payable average, including separate firm results when both firms are selected.
- Supplier ledger, filtered purchase list, edit/cancel, CSV exports, receipt sharing, JSON backup/restore.
- PWA manifest and service worker for install/offline app shell.

## Publish using GitHub Pages
1. Create a **public** repository named `business-payment-calculator`.
2. Upload all files in this folder (`index.html`, `manifest.json`, `service-worker.js`, `icon.svg`, `README.md`) to the repository root.
3. In GitHub, open **Settings → Pages**.
4. Under Build and deployment, choose **Deploy from a branch**, branch **main**, folder **/(root)**, then Save.
5. Wait for the published URL shown in Settings → Pages. Open it in Chrome on Android.
6. Chrome menu (⋮) → **Add to Home screen** or **Install app**.

## Important data limitation
This static GitHub Pages version stores data in the browser's local storage on the current device. It does not synchronize data between phones or users. Use **Reports & Backup → Download full JSON backup** regularly. To share synchronized multi-device records, a shared backend/database and authentication must be added.

## Average price definitions
- Purchase average: sum of (net weight × rate) / sum of net weight, as agreed.
- Effective payable average: sum of final payable / sum of actual quintals.
- Date filters include the selected start and end dates.
