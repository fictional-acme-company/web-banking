<script lang="ts">
  const accounts = [
    { name: 'Everyday Checking', number: '•••• 4821', balance: '$8,420.19' },
    { name: 'High Yield Savings', number: '•••• 1044', balance: '$24,880.73' },
    { name: 'Acme Rewards Card', number: '•••• 7788', balance: '$1,204.40' }
  ];

  const activity = [
    { label: 'Payroll deposit', detail: 'Acme Payroll', amount: '+$4,200.00', tone: 'positive' },
    { label: 'Rent payment', detail: 'Northside Living', amount: '-$2,150.00', tone: 'negative' },
    { label: 'Card purchase', detail: 'City Grocer', amount: '-$82.16', tone: 'negative' }
  ];
</script>

<svelte:head>
  <title>Acme Web Banking</title>
  <meta
    name="description"
    content="Acme Web Banking is a fictional Svelte app for desktop banking workflows."
  />
</svelte:head>

<main class="shell">
  <section class="hero">
    <div>
      <p class="eyebrow">Acme Web Banking</p>
      <h1>Banking that feels calm, fast, and familiar.</h1>
      <p class="lede">
        A fictional Svelte app for checking balances, moving money, and reviewing recent activity
        in one place.
      </p>
    </div>

    <div class="hero-card">
      <div>
        <span class="card-label">Available balance</span>
        <strong>$28,134.52</strong>
      </div>
      <div class="card-actions">
        <button>Transfer</button>
        <button class="secondary">Pay bills</button>
      </div>
    </div>
  </section>

  <section class="grid">
    <article class="panel">
      <div class="panel-head">
        <h2>Accounts</h2>
        <span>Updated just now</span>
      </div>

      <div class="account-list">
        {#each accounts as account}
          <div class="account-row">
            <div>
              <strong>{account.name}</strong>
              <span>{account.number}</span>
            </div>
            <strong>{account.balance}</strong>
          </div>
        {/each}
      </div>
    </article>

    <article class="panel accent">
      <div class="panel-head">
        <h2>Recent activity</h2>
        <span>Last 24 hours</span>
      </div>

      <div class="activity-list">
        {#each activity as item}
          <div class="activity-row">
            <div>
              <strong>{item.label}</strong>
              <span>{item.detail}</span>
            </div>
            <strong class={item.tone === 'positive' ? 'item-positive' : 'item-negative'}>
              {item.amount}
            </strong>
          </div>
        {/each}
      </div>
    </article>
  </section>
</main>

<style>
  .shell {
    min-height: 100vh;
    padding: 48px 20px 64px;
    width: min(1120px, 100%);
    margin: 0 auto;
  }

  .hero {
    display: grid;
    gap: 24px;
    grid-template-columns: minmax(0, 1.8fr) minmax(320px, 1fr);
    align-items: end;
  }

  .eyebrow {
    margin: 0 0 16px;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    font-size: 0.76rem;
    color: rgba(184, 206, 231, 0.72);
  }

  h1 {
    margin: 0;
    font-size: clamp(2.8rem, 7vw, 5.8rem);
    line-height: 0.95;
    max-width: 11ch;
  }

  .lede {
    max-width: 58ch;
    margin: 18px 0 0;
    font-size: 1.08rem;
    line-height: 1.7;
    color: rgba(223, 233, 244, 0.76);
  }

  .hero-card,
  .panel {
    border: 1px solid rgba(189, 212, 232, 0.16);
    background: rgba(7, 16, 28, 0.68);
    backdrop-filter: blur(18px);
    border-radius: 24px;
    box-shadow: 0 22px 60px rgba(1, 8, 17, 0.38);
  }

  .hero-card {
    padding: 24px;
    display: grid;
    gap: 24px;
  }

  .card-label,
  .panel-head span,
  .account-row span,
  .activity-row span {
    color: rgba(191, 210, 229, 0.72);
  }

  .hero-card strong {
    display: block;
    margin-top: 8px;
    font-size: 2.5rem;
  }

  .card-actions {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  button {
    border: 0;
    border-radius: 999px;
    padding: 12px 18px;
    font-weight: 700;
    color: #07111f;
    background: linear-gradient(135deg, #8ed3ff, #f7d37b);
  }

  button.secondary {
    color: rgba(239, 246, 255, 0.94);
    background: rgba(255, 255, 255, 0.08);
    border: 1px solid rgba(255, 255, 255, 0.1);
  }

  .grid {
    margin-top: 28px;
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .panel {
    padding: 24px;
  }

  .panel.accent {
    background: linear-gradient(180deg, rgba(13, 25, 43, 0.92), rgba(9, 16, 28, 0.82));
  }

  .panel-head {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 16px;
    margin-bottom: 18px;
  }

  .panel-head h2 {
    margin: 0;
    font-size: 1.1rem;
  }

  .account-list,
  .activity-list {
    display: grid;
    gap: 14px;
  }

  .account-row,
  .activity-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 18px;
    padding: 16px 18px;
    border-radius: 18px;
    background: rgba(255, 255, 255, 0.04);
  }

  .account-row strong,
  .activity-row strong {
    display: block;
  }

  .item-positive {
    color: #8ff3bf;
  }

  .item-negative {
    color: #ffb4b4;
  }

  @media (max-width: 860px) {
    .hero,
    .grid {
      grid-template-columns: 1fr;
    }

    .shell {
      padding-top: 28px;
    }
  }
</style>