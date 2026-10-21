# Point of Sale for merchants

BlankFX Point of Sale (POS) turns any phone or tablet into a till. You type an amount, the till shows a QR code, your customer pays from their wallet, and the money goes straight to your wallet. The till turns green when the payment arrives.

> **Note:** Point of Sale currently runs on the **Ethereum Sepolia test network**. Payments use test coins with no real value. Use it to try it with your staff before going live.

## What you need before you start

- **A BlankFX account.** Sign up at [demo.blankfx.org](https://demo.blankfx.org).
- **A wallet linked to your account.** Payments can only go to a wallet you have linked under **Settings → Wallets**. Tills never hold keys or funds.
- **An authenticator app** (Google Authenticator, 1Password, Authy or similar), with two-factor authentication turned on in BlankFX. You need a code from it to change where payments go.
- **A phone or tablet for each till**, with a web browser and an internet connection. No app to install.

## Step 1: Set up Point of Sale (once)

1. Sign in and go to **Settings → Point of sale**.
2. Click **Add your first till**.
3. Fill in the **Set up point of sale** form:
   - **Business name**: customers see this when they pay. Use the name on your shop sign.
   - **Country**: two letters, e.g. `CH`.
   - **Settles in**: the currency you want to receive. Customers can pay in any supported coin; you always receive this one.
   - **Paid to**: the wallet your takings go to. Only wallets linked to your account are listed.
4. Click **Continue**. The **Add a till** form opens.

| You choose | You receive |
|---|---|
| USD | USDC |
| EUR | EURC |
| CHF | CHFAU |
| SGD | XSGD |
| JPY | JPY stablecoin |

## Step 2: Add a till

Add one till per counter or device, so each one is easy to tell apart in your reports.

1. In **Settings → Point of sale**, click **Add till** (it opens automatically the first time).
2. Enter the **Shop name**, and optionally the **Address** and **Country**.
3. **Primary currency** and **Paid to** default to your account settings. Change them if this branch should settle differently. Paying a till into a different wallet asks for your two-factor code.
4. Click **Create till**. A **6-digit pairing code** appears.

> **Important:** The pairing code works **once** and expires after **10 minutes**. If it runs out, find the till in the list and click **Show pairing code** for a new one.

## Step 3: Pair the shop's phone or tablet

1. On the device at the counter, open **demo.blankfx.org/pos** in the browser.
2. Type the 6-digit code.
3. Give the till a name staff will recognise, e.g. *Front desk*.
4. Tap **Pair till**.

The till shows your shop name and a green **Online** badge. Tip: add the page to the home screen so staff can open it like an app.

A paired device can only take payments. It cannot move money or see your account.

## Step 4: Take a payment

1. Type the amount on the keypad or keyboard. It works like a cash register: typing `1 2 5 0` gives **12.50**.
2. Optionally add a **Purpose**, e.g. *Coffee*. Customers and your reports show it.
3. Tap **Charge**. The till shows a QR code and a countdown.
4. The customer scans the QR code with their phone and pays from their wallet. If they can't scan, they can type the link shown under **Can't scan? Open this link**.
5. Wait for the till to turn green and show **PAID**. Then hand over the goods.
6. Tap **Done**, or wait 10 seconds. The till returns to the keypad.

> **Important:** Only release goods when the till shows **PAID**. A customer's "Payment sent" screen is not proof: the till is.

### What the customer sees

The customer's page shows your business name, the amount and the purpose. They tap **Connect wallet to pay**, choose a coin and confirm in their wallet. If they pay in a different coin from yours, BlankFX converts it, and you still receive the exact amount you charged. The customer pays their own network fee.

## Customers paying from an exchange account

Some customers hold their coins on an exchange (e.g. Coinbase or Kraken) rather than in a wallet. For them:

1. On the payment screen, switch from **BlankFX checkout** to **Exchange wallet**.
2. The till shows an address and an exact amount to send, e.g. **5.0002 EURC**. The last digits identify this sale, so the customer must send exactly that amount, on the network shown, with the exchange's fee on top.
3. When the customer says they have sent it, tap **Confirm as Sent**. The till shows **Waiting for the exchange**.
4. Release the goods only when the till turns green. Exchange withdrawals can take several minutes.

## What the till's status means

| Till shows | What it means | What to do |
|---|---|---|
| **Awaiting payment** | Waiting for the customer | Keep the QR code on screen |
| **Confirming…** | Payment seen, not yet final | Wait, don't release goods yet |
| **PAID** | Money received | Hand over the goods |
| **PAID (late)** | Paid after the code expired | Check the amount, then hand over |
| **SHORT** | Less than the full amount arrived | Collect the difference |
| **Expired** | No payment in time (10 minutes) | Create a new charge |
| **CANNOT CONFIRM PAYMENTS** | The till lost its connection | Don't release goods. Take card or cash until it reconnects |
| **TILL PAUSED** | Your BlankFX account is not active | Don't release goods. Contact BlankFX |

If a customer paid after a code expired, the payment still counts and appears in your takings.

## See your takings

Once you have a till, **Payments → Point of sale** shows:

- what you took in person today, in total and per shop,
- how many tills are online,
- your 20 most recent payments with their status. **Paid** payments link to the transfer on the block explorer.

## Managing tills

In **Settings → Point of sale → Tills**:

- **Edit**: rename a till or change its address, currency or payout wallet.
- **Pair a new device**: move a till to a new phone or tablet. The old device signs out once the new one pairs.
- **Revoke**: stops a till at once, e.g. if a device is lost. It signs out and can't take payments.

To change where all payments go, use **Change** under **Settles to**. This needs your two-factor code, and only appears when more than one wallet is linked to your account.

## Common questions

**Do I need to buy hardware?** No. Any phone or tablet with a browser works.

**Can staff steal funds through the till?** No. Payments go straight to your linked wallet. A till holds no keys and cannot send money.

**What does it cost?** Customers pay the network fee for their transfer. See [Fees](fees.md) for conversion fees when a customer pays in a different coin.

**Can I get paid into my bank account?** Not yet. Daily bank payouts are coming soon.

**Who do I contact for help?** Email [contact@blankfx.org](mailto:contact@blankfx.org).
