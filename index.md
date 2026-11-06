          HTML



 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 8.4 — Grid & Flexbox Hybrid Dashboard</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Step 2: Outer CSS Grid Container -->
  <div class="dashboard-grid">

    <!-- Step 1: Dashboard Header (Flexbox inside) -->
    <header class="dash-header">
      <div class="brand">
        <span class="brand-icon">⚡</span>
        <span class="brand-name">PulseCore</span>
      </div>

      <div class="search-bar">
        <input type="text" placeholder="Search analytics, logs, reports..." aria-label="Search">
      </div>

      <div class="user-menu">
        <button type="button" class="notif-btn" aria-label="Notifications">🔔</button>
        <div class="profile-info">
          <span class="profile-name">Alex Morgan</span>
          <span class="profile-role">DevOps Lead</span>
        </div>
        <div class="avatar">AM</div>
      </div>
    </header>

    <!-- Step 1: Sidebar Navigation (Flexbox inside) -->
    <aside class="dash-sidebar">
      <nav class="side-nav">
        <a href="#overview" class="nav-item active">
          <span class="icon">📊</span> Overview
        </a>
        <a href="#performance" class="nav-item">
          <span class="icon">⚡</span> Performance
        </a>
        <a href="#deployments" class="nav-item">
          <span class="icon">🚀</span> Deployments
        </a>
        <a href="#security" class="nav-item">
          <span class="icon">🛡️</span> Security
        </a>
        <a href="#settings" class="nav-item">
          <span class="icon">⚙️</span> Settings
        </a>
      </nav>
      <div class="sidebar-footer">
        <div class="status-indicator">
          <span class="dot"></span> Systems Operational
        </div>
      </div>
    </aside>

    <!-- Step 1: Main Content Container -->
    <main class="dash-main">

      <div class="main-title-bar">
        <div>
          <h1>Cluster Infrastructure</h1>
          <p>Real-time node performance and deployment metrics.</p>
        </div>
        <button type="button" class="btn-refresh">↻ Sync Telemetry</button>
      </div>

      <!-- Step 3 & 4: 4 Stat Cards using Flexbox for internal alignment -->
      <section class="stats-wrapper">

        <!-- Stat Card 1 -->
        <article class="stat-card">
          <div class="card-top">
            <span class="stat-title">Total API Calls</span>
            <div class="stat-icon-wrap icon-blue">🌐</div>
          </div>
          <div class="card-bottom">
            <span class="stat-number">4.2M</span>
            <span class="trend-badge positive">+12.4%</span>
          </div>
        </article>

        <!-- Stat Card 2 -->
        <article class="stat-card">
          <div class="card-top">
            <span class="stat-title">Active Pods</span>
            <div class="stat-icon-wrap icon-green">📦</div>
          </div>
          <div class="card-bottom">
            <span class="stat-number">384</span>
            <span class="trend-badge positive">+6</span>
          </div>
        </article>

        <!-- Stat Card 3 -->
        <article class="stat-card">
          <div class="card-top">
            <span class="stat-title">Median Latency</span>
            <div class="stat-icon-wrap icon-amber">⏱️</div>
          </div>
          <div class="card-bottom">
            <span class="stat-number">28ms</span>
            <span class="trend-badge negative">+4ms</span>
          </div>
        </article>

        <!-- Stat Card 4 -->
        <article class="stat-card">
          <div class="card-top">
            <span class="stat-title">Error Rate</span>
            <div class="stat-icon-wrap icon-red">⚠️</div>
          </div>
          <div class="card-bottom">
            <span class="stat-number">0.03%</span>
            <span class="trend-badge positive">-0.01%</span>
          </div>
        </article>

      </section>

      <!-- Step 5: Recent Activity Section with Data Table -->
      <section class="activity-section">
        <div class="section-top">
          <h2>Recent Deployments & Events</h2>
          <a href="#view-all" class="link-more">View full event log →</a>
        </div>

        <div class="table-container">
          <table class="data-table">
            <thead>
              <tr>
                <th>Service Name</th>
                <th>Environment</th>
                <th>Commit</th>
                <th>Status</th>
                <th>Timestamp</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td><strong>auth-service</strong></td>
                <td>Production (us-east-1)</td>
                <td><code>#7f4a0c</code></td>
                <td><span class="badge badge-success">Deployed</span></td>
                <td>4 mins ago</td>
              </tr>
              <tr>
                <td><strong>billing-gateway</strong></td>
                <td>Production (eu-central-1)</td>
                <td><code>#12b88e</code></td>
                <td><span class="badge badge-success">Deployed</span></td>
                <td>22 mins ago</td>
              </tr>
              <tr>
                <td><strong>notification-worker</strong></td>
                <td>Staging (us-west-2)</td>
                <td><code>#e84118</code></td>
                <td><span class="badge badge-warning">Building</span></td>
                <td>35 mins ago</td>
              </tr>
              <tr>
                <td><strong>telemetry-collector</strong></td>
                <td>Production (ap-south-1)</td>
                <td><code>#9c27b0</code></td>
                <td><span class="badge badge-danger">Failed</span></td>
                <td>1 hour ago</td>
              </tr>
            </tbody>
          </table>
        </div>
      </section>

    </main>

  </div>

</body>
</html>




                        CSS


/* --- Global Reset & Variables --- */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary: #2563eb;
  --bg-page: #f8fafc;
  --bg-surface: #ffffff;
  --bg-sidebar: #0f172a;
  --border: #e2e8f0;
  --text-main: #0f172a;
  --text-muted: #64748b;
  --success: #16a34a;
  --warning: #d97706;
  --danger: #dc2626;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  color: var(--text-main);
  background-color: var(--bg-page);
  line-height: 1.5;
}

/* ================= STEP 2: OUTER CSS GRID LAYOUT ================= */
.dashboard-grid {
  display: grid;
  /* 
    Column 1: 250px fixed navigation rail
    Column 2: 1fr flexible workspace
  */
  grid-template-columns: 250px 1fr;
  /* 
    Row 1: 68px top navigation bar
    Row 2: 1fr expands to occupy remaining vertical space
  */
  grid-template-rows: 68px 1fr;
  min-height: 100vh;
}

/* ================= STEP 1: HEADER (Flexbox) ================= */
.dash-header {
  grid-column: 1 / -1;               /* Spans both columns */
  background-color: var(--bg-surface);
  border-bottom: 1px solid var(--border);
  padding: 0 2rem;
  
  /* Flexbox for horizontal layout */
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 2rem;
}

.brand {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1.25rem;
  font-weight: 800;
  color: var(--text-main);
}

.brand-icon {
  font-size: 1.3rem;
}

.search-bar {
  flex: 0 1 420px;
}

.search-bar input {
  width: 100%;
  padding: 0.55rem 1rem;
  border: 1px solid var(--border);
  border-radius: 8px;
  background-color: var(--bg-page);
  font-size: 0.9rem;
  outline: none;
}

.search-bar input:focus {
  border-color: var(--primary);
}

.user-menu {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.notif-btn {
  background: none;
  border: none;
  font-size: 1.2rem;
  cursor: pointer;
  padding: 0.35rem;
}

.profile-info {
  display: flex;
  flex-direction: column;
  text-align: right;
}

.profile-name {
  font-size: 0.875rem;
  font-weight: 700;
}

.profile-role {
  font-size: 0.75rem;
  color: var(--text-muted);
}

.avatar {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: #e0e7ff;
  color: var(--primary);
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 0.85rem;
}

/* ================= STEP 1: SIDEBAR (Flexbox) ================= */
.dash-sidebar {
  background-color: var(--bg-sidebar);
  border-right: 1px solid #1e293b;
  padding: 1.5rem 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.side-nav {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}

.nav-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.7rem 1rem;
  color: #94a3b8;
  text-decoration: none;
  border-radius: 8px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: all 0.2s ease;
}

.nav-item:hover {
  background-color: #1e293b;
  color: #ffffff;
}

.nav-item.active {
  background-color: var(--primary);
  color: #ffffff;
}

.sidebar-footer {
  padding-top: 1rem;
  border-top: 1px solid #1e293b;
}

.status-indicator {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.8rem;
  color: #94a3b8;
}

.dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background-color: #22c55e;
}

/* ================= STEP 1: MAIN WORKSPACE ================= */
.dash-main {
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  overflow-y: auto;
}

.main-title-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.main-title-bar h1 {
  font-size: 1.75rem;
  font-weight: 800;
  letter-spacing: -0.02em;
}

.main-title-bar p {
  color: var(--text-muted);
  font-size: 0.95rem;
  margin-top: 0.2rem;
}

.btn-refresh {
  background-color: var(--bg-surface);
  border: 1px solid var(--border);
  padding: 0.6rem 1rem;
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s;
}

.btn-refresh:hover {
  background-color: #f1f5f9;
}

/* ================= STEP 3 & 4: STAT CARDS (Grid Outer + Flex Inner) ================= */
.stats-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
}

/* Step 4: Aligning icons, titles, and numbers using Flexbox inside cards */
.stat-card {
  background-color: var(--bg-surface);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.03);
  
  /* Flex vertical column to space top and bottom */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 1.25rem;
}

.card-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.stat-title {
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--text-muted);
}

.stat-icon-wrap {
  width: 38px;
  height: 38px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.1rem;
}

.icon-blue  { background-color: #eff6ff; }
.icon-green { background-color: #f0fdf4; }
.icon-amber { background-color: #fffbeb; }
.icon-red   { background-color: #fef2f2; }

.card-bottom {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}

.stat-number {
  font-size: 1.85rem;
  font-weight: 800;
  letter-spacing: -0.02em;
}

.trend-badge {
  font-size: 0.75rem;
  font-weight: 700;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
}

.trend-badge.positive {
  background-color: #dcfce7;
  color: var(--success);
}

.trend-badge.negative {
  background-color: #fee2e2;
  color: var(--danger);
}

/* ================= STEP 5: RECENT ACTIVITY & TABLE ================= */
.activity-section {
  background-color: var(--bg-surface);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.03);
}

.section-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.25rem;
}

.section-top h2 {
  font-size: 1.15rem;
  font-weight: 700;
}

.link-more {
  text-decoration: none;
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--primary);
}

.table-container {
  overflow-x: auto;
}

.data-table {
  width: 100%;
  border-collapse: collapse;
  text-align: left;
  font-size: 0.9rem;
}

.data-table th {
  padding: 0.75rem 1rem;
  background-color: var(--bg-page);
  color: var(--text-muted);
  font-weight: 600;
  border-bottom: 1px solid var(--border);
}

.data-table td {
  padding: 1rem;
  border-bottom: 1px solid var(--border);
  color: #334155;
}

.data-table tr:last-child td {
  border-bottom: none;
}

.data-table code {
  font-family: SFMono-Regular, Consolas, monospace;
  background-color: #f1f5f9;
  padding: 0.2rem 0.4rem;
  border-radius: 4px;
  font-size: 0.85em;
}

.badge {
  display: inline-block;
  padding: 0.25rem 0.6rem;
  border-radius: 9999px;
  font-size: 0.75rem;
  font-weight: 700;
}

.badge-success { background-color: #dcfce7; color: var(--success); }
.badge-warning { background-color: #fef3c7; color: var(--warning); }
.badge-danger  { background-color: #fee2e2; color: var(--danger); }

/* ================= RESPONSIVE BEHAVIOR ================= */
@media (max-width: 820px) {
  .dashboard-grid {
    grid-template-columns: 1fr;
    grid-template-rows: auto auto 1fr;
  }

  .search-bar {
    display: none;
  }

  .dash-sidebar {
    padding: 0.75rem;
  }

  .side-nav {
    flex-direction: row;
    overflow-x: auto;
  }

  .sidebar-footer {
    display: none;
  }

  .dash-main {
    padding: 1.25rem;
  }
}