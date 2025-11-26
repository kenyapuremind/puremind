<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Record Book - Enhanced Finance Management</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #228B22; /* Golden Green */
            --primary-light: #32CD32;
            --primary-dark: #006400;
            --secondary: #DAA520; /* Golden */
            --success: #228B22; /* Golden Green */
            --danger: #DC143C; /* Crimson */
            --warning: #FF8C00; /* Dark Orange */
            --light: #f5f5f5;
            --dark: #212121;
            --text: #212121;
            --text-light: #757575;
            --border: #e0e0e0;
            --shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            --white: #ffffff;
            --black: #000000;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--white);
            color: var(--text);
            line-height: 1.6;
            font-size: 14px;
        }

        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 0 10px;
        }

        /* Header Styles */
        header {
            background-color: var(--primary);
            color: var(--white);
            padding: 10px 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.2rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }

        .logo i {
            margin-right: 8px;
            color: var(--white);
        }

        .user-info {
            display: flex;
            align-items: center;
            font-size: 0.9rem;
        }

        .user-info img {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            margin-right: 8px;
            border: 2px solid var(--white);
        }

        /* Navigation */
        nav {
            background-color: var(--white);
            box-shadow: var(--shadow);
            margin-bottom: 15px;
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
            border-bottom: 2px solid var(--primary);
        }

        .nav-container {
            display: flex;
            min-width: max-content;
            padding: 8px 0;
        }

        .nav-item {
            padding: 8px 15px;
            white-space: nowrap;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s;
            font-size: 0.9rem;
            color: var(--text);
        }

        .nav-item.active {
            border-bottom-color: var(--secondary);
            color: var(--primary);
            font-weight: 600;
        }

        .nav-item:hover {
            background-color: var(--light);
            color: var(--primary);
        }

        /* Main Content */
        .main-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        @media (min-width: 768px) {
            .main-content {
                grid-template-columns: 1fr 250px;
            }
        }

        /* Card Styles */
        .card {
            background-color: var(--white);
            border-radius: 6px;
            box-shadow: var(--shadow);
            padding: 15px;
            margin-bottom: 15px;
            border: 1px solid var(--border);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
            padding-bottom: 8px;
            border-bottom: 1px solid var(--border);
            flex-wrap: wrap;
            gap: 10px;
        }

        .card-title {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--primary);
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 12px;
        }

        label {
            display: block;
            margin-bottom: 4px;
            font-weight: 500;
            font-size: 0.9rem;
            color: var(--text);
        }

        input, select, textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid var(--border);
            border-radius: 4px;
            font-size: 0.9rem;
            background-color: var(--white);
            color: var(--text);
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(34, 139, 34, 0.1);
        }

        button {
            padding: 8px 12px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.9rem;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
        }

        .btn-primary {
            background-color: var(--primary);
            color: var(--white);
        }

        .btn-success {
            background-color: var(--success);
            color: var(--white);
        }

        .btn-danger {
            background-color: var(--danger);
            color: var(--white);
        }

        .btn-warning {
            background-color: var(--warning);
            color: var(--white);
        }

        .btn-secondary {
            background-color: var(--secondary);
            color: var(--white);
        }

        button:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(0);
        }

        /* Table Styles */
        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.85rem;
        }

        th, td {
            padding: 8px 10px;
            text-align: left;
            border-bottom: 1px solid var(--border);
        }

        th {
            background-color: var(--light);
            font-weight: 600;
            color: var(--text);
        }

        tr:hover {
            background-color: rgba(0, 0, 0, 0.02);
        }

        .action-buttons {
            display: flex;
            gap: 4px;
            flex-wrap: wrap;
        }

        .action-btn {
            padding: 4px 8px;
            font-size: 0.75rem;
        }

        /* Dashboard Stats */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 12px;
            margin-bottom: 15px;
        }

        .stat-card {
            background-color: var(--white);
            border-radius: 6px;
            box-shadow: var(--shadow);
            padding: 15px;
            text-align: center;
            border: 1px solid var(--border);
        }

        .stat-value {
            font-size: 1.5rem;
            font-weight: 700;
            margin: 8px 0;
            color: var(--primary);
        }

        .stat-label {
            color: var(--text-light);
            font-size: 0.8rem;
        }

        /* Tabs */
        .tabs {
            display: flex;
            border-bottom: 1px solid var(--border);
            margin-bottom: 15px;
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
        }

        .tab {
            padding: 8px 15px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            white-space: nowrap;
            font-size: 0.9rem;
            color: var(--text);
        }

        .tab.active {
            border-bottom-color: var(--secondary);
            color: var(--primary);
            font-weight: 600;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Search and Filter */
        .search-filter {
            display: flex;
            gap: 8px;
            margin-bottom: 12px;
            flex-wrap: wrap;
        }

        .search-box {
            flex: 1;
            min-width: 150px;
        }

        .filter-select {
            min-width: 120px;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 10px;
        }

        .modal-content {
            background-color: var(--white);
            border-radius: 6px;
            width: 100%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            padding: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            border: 1px solid var(--border);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 8px;
            border-bottom: 1px solid var(--border);
        }

        .modal-title {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary);
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.3rem;
            cursor: pointer;
            color: var(--text-light);
        }

        /* Footer */
        footer {
            background-color: var(--primary);
            color: var(--white);
            text-align: center;
            padding: 15px 0;
            margin-top: 30px;
            font-size: 0.8rem;
        }

        /* Utility Classes */
        .text-center {
            text-align: center;
        }

        .text-right {
            text-align: right;
        }

        .mb-0 {
            margin-bottom: 0;
        }

        .mt-20 {
            margin-top: 15px;
        }

        .hidden {
            display: none;
        }

        /* Toast Notifications */
        .toast {
            position: fixed;
            bottom: 15px;
            right: 15px;
            left: 15px;
            padding: 12px 15px;
            background-color: var(--primary);
            color: var(--white);
            border-radius: 4px;
            box-shadow: var(--shadow);
            z-index: 1100;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s;
            text-align: center;
            font-size: 0.9rem;
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        .toast.error {
            background-color: var(--danger);
        }

        /* Status Badges */
        .status-badge {
            padding: 3px 6px;
            border-radius: 3px;
            font-size: 0.75rem;
            font-weight: 600;
        }

        .status-badge.paid, .status-badge.in-stock, .status-badge.active {
            background-color: rgba(34, 139, 34, 0.2);
            color: var(--primary);
        }

        .status-badge.pending, .status-badge.low-stock {
            background-color: rgba(255, 140, 0, 0.2);
            color: var(--warning);
        }

        .status-badge.overdue, .status-badge.out-of-stock, .status-badge.inactive {
            background-color: rgba(220, 20, 60, 0.2);
            color: var(--danger);
        }

        /* Delete Confirmation Modal */
        .confirmation-modal .modal-content {
            max-width: 350px;
        }

        .confirmation-actions {
            display: flex;
            justify-content: flex-end;
            gap: 8px;
            margin-top: 15px;
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 30px 15px;
            color: var(--text-light);
        }

        .empty-state i {
            font-size: 2.5rem;
            margin-bottom: 12px;
            color: var(--border);
        }

        .empty-state p {
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        /* Form Layout */
        .form-row {
            display: flex;
            gap: 12px;
            margin-bottom: 12px;
            flex-wrap: wrap;
        }

        .form-row .form-group {
            flex: 1;
            margin-bottom: 0;
            min-width: 120px;
        }

        /* Chat Styles */
        .chat-container {
            background-color: var(--white);
            border-radius: 6px;
            box-shadow: var(--shadow);
            padding: 15px;
            margin-top: 15px;
            border: 1px solid var(--border);
        }

        .chat-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
            padding-bottom: 8px;
            border-bottom: 1px solid var(--border);
        }

        .chat-messages {
            height: 250px;
            overflow-y: auto;
            margin-bottom: 12px;
            padding: 8px;
            border: 1px solid var(--border);
            border-radius: 4px;
            background-color: var(--light);
        }

        .message {
            margin-bottom: 12px;
            padding: 8px;
            border-radius: 6px;
            max-width: 85%;
            font-size: 0.9rem;
        }

        .message.user {
            background-color: var(--primary);
            color: var(--white);
            margin-left: auto;
        }

        .message.system {
            background-color: var(--white);
            color: var(--text);
            border: 1px solid var(--border);
        }

        .chat-input {
            display: flex;
            gap: 8px;
        }

        .chat-input input {
            flex: 1;
        }

        /* Category Management */
        .category-list {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }

        .category-tag {
            background-color: var(--light);
            padding: 4px 8px;
            border-radius: 15px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 4px;
            border: 1px solid var(--border);
        }

        .category-tag .remove {
            cursor: pointer;
            color: var(--danger);
        }

        /* Button Groups */
        .button-group {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        /* File Input */
        .file-input-container {
            position: relative;
            display: inline-block;
        }

        .file-input {
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }

        /* Mobile-specific adjustments */
        @media (max-width: 480px) {
            .card-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .button-group {
                width: 100%;
                justify-content: space-between;
            }
            
            .button-group button {
                flex: 1;
                min-width: 0;
            }
            
            .action-buttons {
                justify-content: center;
            }
            
            .stats-container {
                grid-template-columns: 1fr 1fr;
            }
            
            .search-filter {
                flex-direction: column;
            }
            
            .search-box, .filter-select {
                min-width: 100%;
            }
        }

        /* Very small screens */
        @media (max-width: 360px) {
            .nav-item {
                padding: 6px 10px;
                font-size: 0.8rem;
            }
            
            .stats-container {
                grid-template-columns: 1fr;
            }
            
            .action-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Main App -->
    <div id="mainApp">
        <header>
            <div class="container header-content">
                <div class="logo">
                    <i class="fas fa-book"></i> The Record Book - Enhanced
                </div>
                <div class="user-info">
                    <img src="https://ui-avatars.com/api/?name=Business+Owner&background=228B22&color=fff" alt="User">
                    <span>Business Owner</span>
                </div>
            </div>
        </header>

        <nav>
            <div class="container nav-container">
                <div class="nav-item active" data-tab="dashboard">Dashboard</div>
                <div class="nav-item" data-tab="invoices">Invoices</div>
                <div class="nav-item" data-tab="bills">Bills</div>
                <div class="nav-item" data-tab="inventory">Inventory</div>
                <div class="nav-item" data-tab="employees">Employees</div>
                <div class="nav-item" data-tab="customers">Customers</div>
                <div class="nav-item" data-tab="vendors">Vendors</div>
                <div class="nav-item" data-tab="categories">Categories</div>
                <div class="nav-item" data-tab="transactions">Transactions</div>
                <div class="nav-item" data-tab="reports">Reports</div>
                <div class="nav-item" data-tab="settings">Settings</div>
                <div class="nav-item" data-tab="tax">Tax Management</div>
            </div>
        </nav>

        <div class="container">
            <div class="main-content">
                <div>
                    <!-- Dashboard Tab -->
                    <div id="dashboard" class="tab-content active">
                        <div class="stats-container">
                            <div class="stat-card">
                                <div class="stat-label">Total Sales</div>
                                <div class="stat-value" id="totalSales">KSh 0</div>
                                <div class="stat-label">This Month</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-label">Pending Invoices</div>
                                <div class="stat-value" id="pendingInvoices">0</div>
                                <div class="stat-label" id="pendingInvoicesAmount">KSh 0</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-label">Inventory Items</div>
                                <div class="stat-value" id="inventoryItems">0</div>
                                <div class="stat-label" id="lowStockItems">0 Low Stock</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-label">Employees</div>
                                <div class="stat-value" id="totalEmployees">0</div>
                                <div class="stat-label" id="activeEmployees">0 Active</div>
                            </div>
                        </div>

                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Recent Transactions</div>
                                <button class="btn-primary" onclick="navigateToTab('transactions')">View All</button>
                            </div>
                            <div class="table-responsive">
                                <table>
                                    <thead>
                                        <tr>
                                            <th>Date</th>
                                            <th>Description</th>
                                            <th>Type</th>
                                            <th>Amount</th>
                                            <th>Status</th>
                                        </tr>
                                    </thead>
                                    <tbody id="recentTransactions">
                                        <!-- Transactions will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="transactionsEmptyState" class="empty-state">
                                <i class="fas fa-exchange-alt"></i>
                                <h3>No Recent Transactions</h3>
                                <p>Your recent transactions will appear here.</p>
                            </div>
                        </div>

                        <!-- Quick Support Section -->
                        <div class="chat-container">
                            <div class="chat-header">
                                <div class="card-title">Quick Support</div>
                                <button class="btn-primary" onclick="clearChat()">Clear Chat</button>
                            </div>
                            <div class="chat-messages" id="chatMessages">
                                <div class="message system">
                                    <strong>System:</strong> Welcome to The Record Book! How can I help you today?
                                </div>
                            </div>
                            <div class="chat-input">
                                <input type="text" id="chatInput" placeholder="Type your message..." onkeypress="handleChatKeypress(event)">
                                <button class="btn-primary" onclick="sendMessage()">Send</button>
                            </div>
                        </div>
                    </div>

                    <!-- Invoices Tab -->
                    <div id="invoices" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Invoices</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showInvoiceForm()"><i class="fas fa-plus"></i> New Invoice</button>
                                    <div class="file-input-container">
                                        <button class="btn-warning"><i class="fas fa-file-import"></i> Import</button>
                                        <input type="file" id="invoiceCsvInput" class="file-input" accept=".csv" onchange="importCSV('invoices', this)">
                                    </div>
                                    <button class="btn-success" onclick="exportToCsv('invoices')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('invoices')"><i class="fas fa-trash"></i> Delete All</button>
                                    <button class="btn-secondary" onclick="generateSampleData()"><i class="fas fa-database"></i> Sample Data</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="invoiceSearch" placeholder="Search invoices..." onkeyup="filterInvoices()">
                                </div>
                                <select class="filter-select" id="invoiceStatusFilter" onchange="filterInvoices()">
                                    <option value="all">All Status</option>
                                    <option value="paid">Paid</option>
                                    <option value="pending">Pending</option>
                                    <option value="overdue">Overdue</option>
                                </select>
                                <select class="filter-select" id="invoiceClientFilter" onchange="filterInvoices()">
                                    <option value="all">All Clients</option>
                                </select>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="invoicesTable">
                                    <thead>
                                        <tr>
                                            <th>Invoice #</th>
                                            <th>Client</th>
                                            <th>Date</th>
                                            <th>Due Date</th>
                                            <th>Amount</th>
                                            <th>Status</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="invoicesTableBody">
                                        <!-- Invoices will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="invoicesEmptyState" class="empty-state">
                                <i class="fas fa-file-invoice"></i>
                                <h3>No Invoices Found</h3>
                                <p>You haven't created any invoices yet. Create your first invoice to get started.</p>
                                <button class="btn-primary" onclick="showInvoiceForm()">Create Invoice</button>
                            </div>
                        </div>
                    </div>

                    <!-- Bills Tab -->
                    <div id="bills" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Bills</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showBillForm()"><i class="fas fa-plus"></i> New Bill</button>
                                    <div class="file-input-container">
                                        <button class="btn-warning"><i class="fas fa-file-import"></i> Import</button>
                                        <input type="file" id="billsCsvInput" class="file-input" accept=".csv" onchange="importCSV('bills', this)">
                                    </div>
                                    <button class="btn-success" onclick="exportToCsv('bills')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('bills')"><i class="fas fa-trash"></i> Delete All</button>
                                    <button class="btn-secondary" onclick="generateSampleData()"><i class="fas fa-database"></i> Sample Data</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="billsSearch" placeholder="Search bills..." onkeyup="filterBills()">
                                </div>
                                <select class="filter-select" id="billStatusFilter" onchange="filterBills()">
                                    <option value="all">All Status</option>
                                    <option value="paid">Paid</option>
                                    <option value="pending">Pending</option>
                                    <option value="overdue">Overdue</option>
                                </select>
                                <select class="filter-select" id="billVendorFilter" onchange="filterBills()">
                                    <option value="all">All Vendors</option>
                                </select>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="billsTable">
                                    <thead>
                                        <tr>
                                            <th>Bill #</th>
                                            <th>Vendor</th>
                                            <th>Date</th>
                                            <th>Due Date</th>
                                            <th>Amount</th>
                                            <th>Status</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="billsTableBody">
                                        <!-- Bills will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="billsEmptyState" class="empty-state">
                                <i class="fas fa-receipt"></i>
                                <h3>No Bills Found</h3>
                                <p>You haven't created any bills yet. Create your first bill to get started.</p>
                                <button class="btn-primary" onclick="showBillForm()">Create Bill</button>
                            </div>
                        </div>
                    </div>

                    <!-- Inventory Tab -->
                    <div id="inventory" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Inventory Management</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showInventoryForm()"><i class="fas fa-plus"></i> Add Item</button>
                                    <button class="btn-success" onclick="exportToCsv('inventory')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('inventory')"><i class="fas fa-trash"></i> Delete All</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="inventorySearch" placeholder="Search inventory..." onkeyup="filterInventory()">
                                </div>
                                <select class="filter-select" id="inventoryStatusFilter" onchange="filterInventory()">
                                    <option value="all">All Status</option>
                                    <option value="in-stock">In Stock</option>
                                    <option value="low-stock">Low Stock</option>
                                    <option value="out-of-stock">Out of Stock</option>
                                </select>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="inventoryTable">
                                    <thead>
                                        <tr>
                                            <th>Item Name</th>
                                            <th>SKU</th>
                                            <th>Category</th>
                                            <th>Quantity</th>
                                            <th>Price</th>
                                            <th>Status</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="inventoryTableBody">
                                        <!-- Inventory items will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="inventoryEmptyState" class="empty-state">
                                <i class="fas fa-boxes"></i>
                                <h3>No Inventory Items</h3>
                                <p>You haven't added any inventory items yet. Add your first item to get started.</p>
                                <button class="btn-primary" onclick="showInventoryForm()">Add Inventory Item</button>
                            </div>
                        </div>
                    </div>

                    <!-- Employees Tab -->
                    <div id="employees" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Employee Management</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showEmployeeForm()"><i class="fas fa-plus"></i> Add Employee</button>
                                    <button class="btn-success" onclick="exportToCsv('employees')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('employees')"><i class="fas fa-trash"></i> Delete All</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="employeeSearch" placeholder="Search employees..." onkeyup="filterEmployees()">
                                </div>
                                <select class="filter-select" id="employeeStatusFilter" onchange="filterEmployees()">
                                    <option value="all">All Status</option>
                                    <option value="active">Active</option>
                                    <option value="inactive">Inactive</option>
                                </select>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="employeesTable">
                                    <thead>
                                        <tr>
                                            <th>Name</th>
                                            <th>Position</th>
                                            <th>Department</th>
                                            <th>Email</th>
                                            <th>Phone</th>
                                            <th>Status</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="employeesTableBody">
                                        <!-- Employees will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="employeesEmptyState" class="empty-state">
                                <i class="fas fa-users"></i>
                                <h3>No Employees</h3>
                                <p>You haven't added any employees yet. Add your first employee to get started.</p>
                                <button class="btn-primary" onclick="showEmployeeForm()">Add Employee</button>
                            </div>
                        </div>
                    </div>

                    <!-- Customers Tab -->
                    <div id="customers" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Customer Management</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showCustomerForm()"><i class="fas fa-plus"></i> Add Customer</button>
                                    <button class="btn-success" onclick="exportToCsv('customers')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('customers')"><i class="fas fa-trash"></i> Delete All</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="customerSearch" placeholder="Search customers..." onkeyup="filterCustomers()">
                                </div>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="customersTable">
                                    <thead>
                                        <tr>
                                            <th>Name</th>
                                            <th>Email</th>
                                            <th>Phone</th>
                                            <th>Company</th>
                                            <th>Total Spent</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="customersTableBody">
                                        <!-- Customers will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="customersEmptyState" class="empty-state">
                                <i class="fas fa-user-friends"></i>
                                <h3>No Customers</h3>
                                <p>You haven't added any customers yet. Add your first customer to get started.</p>
                                <button class="btn-primary" onclick="showCustomerForm()">Add Customer</button>
                            </div>
                        </div>
                    </div>

                    <!-- Vendors Tab -->
                    <div id="vendors" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Vendor Management</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showVendorForm()"><i class="fas fa-plus"></i> Add Vendor</button>
                                    <button class="btn-success" onclick="exportToCsv('vendors')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('vendors')"><i class="fas fa-trash"></i> Delete All</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="vendorSearch" placeholder="Search vendors..." onkeyup="filterVendors()">
                                </div>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="vendorsTable">
                                    <thead>
                                        <tr>
                                            <th>Name</th>
                                            <th>Email</th>
                                            <th>Phone</th>
                                            <th>Category</th>
                                            <th>Total Billed</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="vendorsTableBody">
                                        <!-- Vendors will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="vendorsEmptyState" class="empty-state">
                                <i class="fas fa-truck"></i>
                                <h3>No Vendors</h3>
                                <p>You haven't added any vendors yet. Add your first vendor to get started.</p>
                                <button class="btn-primary" onclick="showVendorForm()">Add Vendor</button>
                            </div>
                        </div>
                    </div>

                    <!-- Categories Tab -->
                    <div id="categories" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Category Management</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showCategoryForm()"><i class="fas fa-plus"></i> Add Category</button>
                                    <button class="btn-danger" onclick="deleteAllItems('categories')"><i class="fas fa-trash"></i> Delete All</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="categorySearch" placeholder="Search categories..." onkeyup="filterCategories()">
                                </div>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="categoriesTable">
                                    <thead>
                                        <tr>
                                            <th>Name</th>
                                            <th>Type</th>
                                            <th>Description</th>
                                            <th>Items Count</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="categoriesTableBody">
                                        <!-- Categories will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="categoriesEmptyState" class="empty-state">
                                <i class="fas fa-tags"></i>
                                <h3>No Categories</h3>
                                <p>You haven't added any categories yet. Add your first category to get started.</p>
                                <button class="btn-primary" onclick="showCategoryForm()">Add Category</button>
                            </div>
                        </div>
                    </div>

                    <!-- Transactions Tab -->
                    <div id="transactions" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Transaction History</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showTransactionForm()"><i class="fas fa-plus"></i> Add Transaction</button>
                                    <button class="btn-success" onclick="exportToCsv('transactions')"><i class="fas fa-file-export"></i> Export</button>
                                    <button class="btn-danger" onclick="deleteAllItems('transactions')"><i class="fas fa-trash"></i> Delete All</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="search-box">
                                    <input type="text" id="transactionSearch" placeholder="Search transactions..." onkeyup="filterTransactions()">
                                </div>
                                <select class="filter-select" id="transactionTypeFilter" onchange="filterTransactions()">
                                    <option value="all">All Types</option>
                                    <option value="income">Income</option>
                                    <option value="expense">Expense</option>
                                </select>
                                <select class="filter-select" id="transactionCategoryFilter" onchange="filterTransactions()">
                                    <option value="all">All Categories</option>
                                </select>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="transactionsTable">
                                    <thead>
                                        <tr>
                                            <th>Date</th>
                                            <th>Description</th>
                                            <th>Category</th>
                                            <th>Type</th>
                                            <th>Amount</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="transactionsTableBody">
                                        <!-- Transactions will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            <div id="transactionsEmptyState" class="empty-state">
                                <i class="fas fa-exchange-alt"></i>
                                <h3>No Transactions</h3>
                                <p>You haven't recorded any transactions yet. Add your first transaction to get started.</p>
                                <button class="btn-primary" onclick="showTransactionForm()">Add Transaction</button>
                            </div>
                        </div>
                    </div>

                    <!-- Reports Tab -->
                    <div id="reports" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Financial Reports</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="generateSalesReport()"><i class="fas fa-chart-line"></i> Sales Report</button>
                                    <button class="btn-success" onclick="generateExpenseReport()"><i class="fas fa-chart-pie"></i> Expense Report</button>
                                    <button class="btn-warning" onclick="generateProfitLossReport()"><i class="fas fa-chart-bar"></i> P&L Report</button>
                                    <button class="btn-secondary" onclick="generateTaxReport()"><i class="fas fa-file-invoice-dollar"></i> Tax Report</button>
                                </div>
                            </div>
                            
                            <div class="search-filter">
                                <div class="form-row">
                                    <div class="form-group">
                                        <label for="reportStartDate">Start Date</label>
                                        <input type="date" id="reportStartDate">
                                    </div>
                                    <div class="form-group">
                                        <label for="reportEndDate">End Date</label>
                                        <input type="date" id="reportEndDate">
                                    </div>
                                    <div class="form-group">
                                        <label for="reportType">Report Type</label>
                                        <select id="reportType">
                                            <option value="sales">Sales Report</option>
                                            <option value="expenses">Expense Report</option>
                                            <option value="profit">Profit & Loss</option>
                                            <option value="tax">Tax Report</option>
                                        </select>
                                    </div>
                                    <div class="form-group">
                                        <label>&nbsp;</label>
                                        <button class="btn-primary" onclick="generateReport()">Generate Report</button>
                                    </div>
                                </div>
                            </div>
                            
                            <div id="reportResults" class="card">
                                <div class="card-header">
                                    <div class="card-title">Report Results</div>
                                </div>
                                <div id="reportContent">
                                    <div class="empty-state">
                                        <i class="fas fa-chart-bar"></i>
                                        <h3>No Report Generated</h3>
                                        <p>Select a report type and date range, then click "Generate Report" to view your financial data.</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Settings Tab -->
                    <div id="settings" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Application Settings</div>
                            </div>
                            
                            <div class="form-group">
                                <label for="businessName">Business Name</label>
                                <input type="text" id="businessName" placeholder="Enter your business name">
                            </div>
                            
                            <div class="form-group">
                                <label for="businessAddress">Business Address</label>
                                <textarea id="businessAddress" rows="3" placeholder="Enter your business address"></textarea>
                            </div>
                            
                            <div class="form-row">
                                <div class="form-group">
                                    <label for="businessPhone">Phone Number</label>
                                    <input type="text" id="businessPhone" placeholder="Enter phone number">
                                </div>
                                <div class="form-group">
                                    <label for="businessEmail">Email Address</label>
                                    <input type="email" id="businessEmail" placeholder="Enter email address">
                                </div>
                            </div>
                            
                            <div class="form-row">
                                <div class="form-group">
                                    <label for="currency">Currency</label>
                                    <select id="currency">
                                        <option value="KSh">Kenyan Shilling (KSh)</option>
                                        <option value="$">US Dollar ($)</option>
                                        <option value="€">Euro (€)</option>
                                        <option value="£">British Pound (£)</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <label for="dateFormat">Date Format</label>
                                    <select id="dateFormat">
                                        <option value="dd/mm/yyyy">DD/MM/YYYY</option>
                                        <option value="mm/dd/yyyy">MM/DD/YYYY</option>
                                        <option value="yyyy-mm-dd">YYYY-MM-DD</option>
                                    </select>
                                </div>
                            </div>
                            
                            <div class="form-group">
                                <label for="taxId">Tax ID/VAT Number</label>
                                <input type="text" id="taxId" placeholder="Enter your tax identification number">
                            </div>
                            
                            <div class="form-group">
                                <button class="btn-primary" onclick="saveSettings()">Save Settings</button>
                                <button class="btn-warning" onclick="resetSettings()">Reset to Default</button>
                                <button class="btn-danger" onclick="clearAllData()">Clear All Data</button>
                            </div>
                        </div>
                    </div>

                    <!-- Tax Management Tab -->
                    <div id="tax" class="tab-content">
                        <div class="card">
                            <div class="card-header">
                                <div class="card-title">Tax Management</div>
                                <div class="button-group">
                                    <button class="btn-primary" onclick="showTaxRuleForm()"><i class="fas fa-plus"></i> Add Tax Rule</button>
                                    <button class="btn-success" onclick="calculateTaxes()"><i class="fas fa-calculator"></i> Calculate Taxes</button>
                                </div>
                            </div>
                            
                            <div class="form-row">
                                <div class="form-group">
                                    <label for="taxYear">Tax Year</label>
                                    <select id="taxYear">
                                        <option value="2023">2023</option>
                                        <option value="2024">2024</option>
                                        <option value="2025">2025</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <label for="taxType">Tax Type</label>
                                    <select id="taxType">
                                        <option value="vat">VAT</option>
                                        <option value="income">Income Tax</option>
                                        <option value="sales">Sales Tax</option>
                                    </select>
                                </div>
                            </div>
                            
                            <div class="table-responsive">
                                <table id="taxRulesTable">
                                    <thead>
                                        <tr>
                                            <th>Tax Name</th>
                                            <th>Rate</th>
                                            <th>Type</th>
                                            <th>Applicable To</th>
                                            <th>Actions</th>
                                        </tr>
                                    </thead>
                                    <tbody id="taxRulesTableBody">
                                        <!-- Tax rules will be populated here -->
                                    </tbody>
                                </table>
                            </div>
                            
                            <div class="card mt-20">
                                <div class="card-header">
                                    <div class="card-title">Tax Calculation Results</div>
                                </div>
                                <div id="taxCalculationResults">
                                    <div class="empty-state">
                                        <i class="fas fa-calculator"></i>
                                        <h3>No Tax Calculations</h3>
                                        <p>Click "Calculate Taxes" to see your tax obligations for the selected period.</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                </div>

                <!-- Sidebar -->
                <div>
                    <!-- Report Chat Section -->
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">Report Assistant</div>
                        </div>
                        <div class="chat-messages" id="reportChatMessages" style="height: 200px; margin-bottom: 12px;">
                            <div class="message system">
                                <strong>Assistant:</strong> Need help with reports? Ask me anything about your financial data.
                            </div>
                        </div>
                        <div class="chat-input">
                            <input type="text" id="reportChatInput" placeholder="Ask about reports..." onkeypress="handleReportChatKeypress(event)">
                            <button class="btn-primary" onclick="sendReportMessage()">Send</button>
                        </div>
                    </div>

                    <!-- Quick Actions -->
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">Quick Actions</div>
                        </div>
                        <div style="display: flex; flex-direction: column; gap: 8px;">
                            <button class="btn-primary" onclick="showInvoiceForm()"><i class="fas fa-file-invoice"></i> Create Invoice</button>
                            <button class="btn-primary" onclick="showBillForm()"><i class="fas fa-receipt"></i> Create Bill</button>
                            <button class="btn-success" onclick="showInventoryForm()"><i class="fas fa-boxes"></i> Add Inventory</button>
                            <button class="btn-primary" onclick="showEmployeeForm()"><i class="fas fa-user-plus"></i> Add Employee</button>
                            <button class="btn-primary" onclick="showCustomerForm()"><i class="fas fa-user-plus"></i> Add Customer</button>
                            <button class="btn-primary" onclick="showVendorForm()"><i class="fas fa-truck"></i> Add Vendor</button>
                            <button class="btn-primary" onclick="showCategoryForm()"><i class="fas fa-tag"></i> Add Category</button>
                            <button class="btn-primary" onclick="showTransactionForm()"><i class="fas fa-exchange-alt"></i> Add Transaction</button>
                            <button class="btn-primary" onclick="navigateToTab('reports')"><i class="fas fa-chart-bar"></i> View Reports</button>
                            <button class="btn-secondary" onclick="generateSampleData()"><i class="fas fa-database"></i> Generate Sample Data</button>
                        </div>
                    </div>
                    
                    <!-- Recent Activity -->
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">Recent Activity</div>
                        </div>
                        <div style="display: flex; flex-direction: column; gap: 12px;" id="recentActivity">
                            <!-- Recent activity will be populated here -->
                        </div>
                        <div id="recentActivityEmptyState" class="empty-state">
                            <i class="fas fa-history"></i>
                            <h3>No Recent Activity</h3>
                            <p>Your recent activity will appear here.</p>
                        </div>
                    </div>

                    <!-- Keyboard Shortcuts -->
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">Keyboard Shortcuts</div>
                        </div>
                        <div style="font-size: 0.8rem;">
                            <p><strong>Ctrl+N:</strong> New Item</p>
                            <p><strong>Ctrl+S:</strong> Save Data</p>
                            <p><strong>Ctrl+F:</strong> Search</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <footer>
            <div class="container">
                <p>PureMind, The Record Book - Enhanced. All rights reserved.</p>
            </div>
        </footer>
    </div>

    <!-- Invoice Modal -->
    <div id="invoiceModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="invoiceModalTitle">Create New Invoice</h3>
                <button class="close-modal" onclick="closeModal('invoiceModal')">&times;</button>
            </div>
            <form id="invoiceForm">
                <input type="hidden" id="invoiceId">
                <div class="form-group">
                    <label for="invoiceNumber">Invoice Number</label>
                    <input type="text" id="invoiceNumber" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="invoiceDate">Date</label>
                        <input type="date" id="invoiceDate" required>
                    </div>
                    <div class="form-group">
                        <label for="invoiceDueDate">Due Date</label>
                        <input type="date" id="invoiceDueDate" required>
                    </div>
                </div>
                <div class="form-group">
                    <label for="invoiceClient">Client</label>
                    <select id="invoiceClient" required>
                        <option value="">Select Client</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label>Items</label>
                    <div id="invoiceItems">
                        <!-- Invoice items will be added here -->
                    </div>
                    <button type="button" class="btn-primary" onclick="addInvoiceItem()" style="margin-top: 8px;">
                        <i class="fas fa-plus"></i> Add Item
                    </button>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="invoiceVat">VAT Amount</label>
                        <input type="number" id="invoiceVat" step="0.01" min="0" readonly>
                    </div>
                    <div class="form-group">
                        <label for="invoiceTotal">Total Amount</label>
                        <input type="number" id="invoiceTotal" step="0.01" min="0" readonly>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="invoiceNotes">Notes</label>
                    <textarea id="invoiceNotes" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Invoice</button>
                    <button type="button" class="btn-danger" onclick="closeModal('invoiceModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Bill Modal -->
    <div id="billModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="billModalTitle">Create New Bill</h3>
                <button class="close-modal" onclick="closeModal('billModal')">&times;</button>
            </div>
            <form id="billForm">
                <input type="hidden" id="billId">
                <div class="form-group">
                    <label for="billNumber">Bill Number</label>
                    <input type="text" id="billNumber" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="billDate">Date</label>
                        <input type="date" id="billDate" required>
                    </div>
                    <div class="form-group">
                        <label for="billDueDate">Due Date</label>
                        <input type="date" id="billDueDate" required>
                    </div>
                </div>
                <div class="form-group">
                    <label for="billVendor">Vendor</label>
                    <select id="billVendor" required>
                        <option value="">Select Vendor</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label>Items</label>
                    <div id="billItems">
                        <!-- Bill items will be added here -->
                    </div>
                    <button type="button" class="btn-primary" onclick="addBillItem()" style="margin-top: 8px;">
                        <i class="fas fa-plus"></i> Add Item
                    </button>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="billVat">VAT Amount</label>
                        <input type="number" id="billVat" step="0.01" min="0" readonly>
                    </div>
                    <div class="form-group">
                        <label for="billTotal">Total Amount</label>
                        <input type="number" id="billTotal" step="0.01" min="0" readonly>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="billNotes">Notes</label>
                    <textarea id="billNotes" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Bill</button>
                    <button type="button" class="btn-danger" onclick="closeModal('billModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Inventory Modal -->
    <div id="inventoryModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="inventoryModalTitle">Add Inventory Item</h3>
                <button class="close-modal" onclick="closeModal('inventoryModal')">&times;</button>
            </div>
            <form id="inventoryForm">
                <input type="hidden" id="inventoryId">
                <div class="form-group">
                    <label for="inventoryName">Item Name</label>
                    <input type="text" id="inventoryName" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="inventorySku">SKU</label>
                        <input type="text" id="inventorySku" required>
                    </div>
                    <div class="form-group">
                        <label for="inventoryCategory">Category</label>
                        <select id="inventoryCategory" required>
                            <option value="">Select Category</option>
                        </select>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="inventoryQuantity">Quantity</label>
                        <input type="number" id="inventoryQuantity" min="0" required>
                    </div>
                    <div class="form-group">
                        <label for="inventoryPrice">Price</label>
                        <input type="number" id="inventoryPrice" step="0.01" min="0" required>
                    </div>
                </div>
                <div class="form-group">
                    <label for="inventoryDescription">Description</label>
                    <textarea id="inventoryDescription" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Item</button>
                    <button type="button" class="btn-danger" onclick="closeModal('inventoryModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Employee Modal -->
    <div id="employeeModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="employeeModalTitle">Add Employee</h3>
                <button class="close-modal" onclick="closeModal('employeeModal')">&times;</button>
            </div>
            <form id="employeeForm">
                <input type="hidden" id="employeeId">
                <div class="form-group">
                    <label for="employeeName">Full Name</label>
                    <input type="text" id="employeeName" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="employeePosition">Position</label>
                        <input type="text" id="employeePosition" required>
                    </div>
                    <div class="form-group">
                        <label for="employeeDepartment">Department</label>
                        <input type="text" id="employeeDepartment" required>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="employeeEmail">Email</label>
                        <input type="email" id="employeeEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="employeePhone">Phone</label>
                        <input type="text" id="employeePhone" required>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="employeeSalary">Salary</label>
                        <input type="number" id="employeeSalary" step="0.01" min="0" required>
                    </div>
                    <div class="form-group">
                        <label for="employeeStatus">Status</label>
                        <select id="employeeStatus" required>
                            <option value="active">Active</option>
                            <option value="inactive">Inactive</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Employee</button>
                    <button type="button" class="btn-danger" onclick="closeModal('employeeModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Customer Modal -->
    <div id="customerModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="customerModalTitle">Add Customer</h3>
                <button class="close-modal" onclick="closeModal('customerModal')">&times;</button>
            </div>
            <form id="customerForm">
                <input type="hidden" id="customerId">
                <div class="form-group">
                    <label for="customerName">Full Name</label>
                    <input type="text" id="customerName" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="customerEmail">Email</label>
                        <input type="email" id="customerEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="customerPhone">Phone</label>
                        <input type="text" id="customerPhone" required>
                    </div>
                </div>
                <div class="form-group">
                    <label for="customerCompany">Company</label>
                    <input type="text" id="customerCompany">
                </div>
                <div class="form-group">
                    <label for="customerAddress">Address</label>
                    <textarea id="customerAddress" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Customer</button>
                    <button type="button" class="btn-danger" onclick="closeModal('customerModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Vendor Modal -->
    <div id="vendorModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="vendorModalTitle">Add Vendor</h3>
                <button class="close-modal" onclick="closeModal('vendorModal')">&times;</button>
            </div>
            <form id="vendorForm">
                <input type="hidden" id="vendorId">
                <div class="form-group">
                    <label for="vendorName">Vendor Name</label>
                    <input type="text" id="vendorName" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="vendorEmail">Email</label>
                        <input type="email" id="vendorEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="vendorPhone">Phone</label>
                        <input type="text" id="vendorPhone" required>
                    </div>
                </div>
                <div class="form-group">
                    <label for="vendorCategory">Category</label>
                    <input type="text" id="vendorCategory" required>
                </div>
                <div class="form-group">
                    <label for="vendorAddress">Address</label>
                    <textarea id="vendorAddress" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Vendor</button>
                    <button type="button" class="btn-danger" onclick="closeModal('vendorModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Category Modal -->
    <div id="categoryModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="categoryModalTitle">Add Category</h3>
                <button class="close-modal" onclick="closeModal('categoryModal')">&times;</button>
            </div>
            <form id="categoryForm">
                <input type="hidden" id="categoryId">
                <div class="form-group">
                    <label for="categoryName">Category Name</label>
                    <input type="text" id="categoryName" required>
                </div>
                <div class="form-group">
                    <label for="categoryType">Category Type</label>
                    <select id="categoryType" required>
                        <option value="income">Income</option>
                        <option value="expense">Expense</option>
                        <option value="inventory">Inventory</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="categoryDescription">Description</label>
                    <textarea id="categoryDescription" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Category</button>
                    <button type="button" class="btn-danger" onclick="closeModal('categoryModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Transaction Modal -->
    <div id="transactionModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="transactionModalTitle">Add Transaction</h3>
                <button class="close-modal" onclick="closeModal('transactionModal')">&times;</button>
            </div>
            <form id="transactionForm">
                <input type="hidden" id="transactionId">
                <div class="form-group">
                    <label for="transactionDate">Date</label>
                    <input type="date" id="transactionDate" required>
                </div>
                <div class="form-group">
                    <label for="transactionDescription">Description</label>
                    <input type="text" id="transactionDescription" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="transactionType">Type</label>
                        <select id="transactionType" required>
                            <option value="income">Income</option>
                            <option value="expense">Expense</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="transactionCategory">Category</label>
                        <select id="transactionCategory" required>
                            <option value="">Select Category</option>
                        </select>
                    </div>
                </div>
                <div class="form-group">
                    <label for="transactionAmount">Amount</label>
                    <input type="number" id="transactionAmount" step="0.01" required>
                </div>
                <div class="form-group">
                    <label for="transactionNotes">Notes</label>
                    <textarea id="transactionNotes" rows="3"></textarea>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Transaction</button>
                    <button type="button" class="btn-danger" onclick="closeModal('transactionModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Tax Rule Modal -->
    <div id="taxRuleModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="taxRuleModalTitle">Add Tax Rule</h3>
                <button class="close-modal" onclick="closeModal('taxRuleModal')">&times;</button>
            </div>
            <form id="taxRuleForm">
                <input type="hidden" id="taxRuleId">
                <div class="form-group">
                    <label for="taxRuleName">Tax Name</label>
                    <input type="text" id="taxRuleName" required>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="taxRuleRate">Tax Rate (%)</label>
                        <input type="number" id="taxRuleRate" step="0.01" min="0" required>
                    </div>
                    <div class="form-group">
                        <label for="taxRuleType">Tax Type</label>
                        <select id="taxRuleType" required>
                            <option value="vat">VAT</option>
                            <option value="income">Income Tax</option>
                            <option value="sales">Sales Tax</option>
                            <option value="other">Other</option>
                        </select>
                    </div>
                </div>
                <div class="form-group">
                    <label for="taxRuleApplicable">Applicable To</label>
                    <select id="taxRuleApplicable" required>
                        <option value="all">All Transactions</option>
                        <option value="sales">Sales Only</option>
                        <option value="purchases">Purchases Only</option>
                        <option value="services">Services Only</option>
                    </select>
                </div>
                
                <div class="form-group" style="display: flex; gap: 8px; margin-top: 15px;">
                    <button type="submit" class="btn-primary" style="flex: 1;">Save Tax Rule</button>
                    <button type="button" class="btn-danger" onclick="closeModal('taxRuleModal')" style="flex: 1;">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Delete Confirmation Modal -->
    <div id="deleteModal" class="modal confirmation-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Confirm Delete</h3>
                <button class="close-modal" onclick="closeModal('deleteModal')">&times;</button>
            </div>
            <p>Are you sure you want to delete this item? This action cannot be undone.</p>
            <div class="confirmation-actions">
                <button class="btn-danger" onclick="deleteItem()">Delete</button>
                <button class="btn-primary" onclick="closeModal('deleteModal')">Cancel</button>
            </div>
        </div>
    </div>

    <!-- Delete All Confirmation Modal -->
    <div id="deleteAllModal" class="modal confirmation-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Confirm Delete All</h3>
                <button class="close-modal" onclick="closeModal('deleteAllModal')">&times;</button>
            </div>
            <p>Are you sure you want to delete ALL <span id="deleteAllType"></span>? This action cannot be undone.</p>
            <div class="confirmation-actions">
                <button class="btn-danger" onclick="proceedDeleteAll()">Delete All</button>
                <button class="btn-primary" onclick="closeModal('deleteAllModal')">Cancel</button>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div id="toast" class="toast"></div>

    <script>
        // Data storage - All empty arrays
        let invoices = [];
        let bills = [];
        let inventory = [];
        let employees = [];
        let customers = [];
        let vendors = [];
        let categories = [];
        let transactions = [];
        let taxRules = [];
        let settings = {};
        let chatMessages = [
            { sender: 'system', message: 'Welcome to The Record Book! How can I help you today?' }
        ];
        let reportChatMessages = [
            { sender: 'system', message: 'Need help with reports? Ask me anything about your financial data.' }
        ];

        // Track items to be deleted
        let itemToDelete = null;
        let deleteAllType = null;

        // Initialize the app
        document.addEventListener('DOMContentLoaded', function() {
            // Set up navigation
            document.querySelectorAll('.nav-item').forEach(item => {
                item.addEventListener('click', function() {
                    navigateToTab(this.getAttribute('data-tab'));
                });
            });
            
            // Load data from localStorage
            loadFromLocalStorage();
            
            // Set current date as default for forms
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('invoiceDate').value = today;
            document.getElementById('invoiceDueDate').value = today;
            document.getElementById('billDate').value = today;
            document.getElementById('billDueDate').value = today;
            document.getElementById('transactionDate').value = today;
            document.getElementById('reportStartDate').value = today;
            document.getElementById('reportEndDate').value = today;
            
            // Set up form submissions
            document.getElementById('invoiceForm').addEventListener('submit', handleInvoiceSubmit);
            document.getElementById('billForm').addEventListener('submit', handleBillSubmit);
            document.getElementById('inventoryForm').addEventListener('submit', handleInventorySubmit);
            document.getElementById('employeeForm').addEventListener('submit', handleEmployeeSubmit);
            document.getElementById('customerForm').addEventListener('submit', handleCustomerSubmit);
            document.getElementById('vendorForm').addEventListener('submit', handleVendorSubmit);
            document.getElementById('categoryForm').addEventListener('submit', handleCategorySubmit);
            document.getElementById('transactionForm').addEventListener('submit', handleTransactionSubmit);
            document.getElementById('taxRuleForm').addEventListener('submit', handleTaxRuleSubmit);
            
            // Set up VAT calculation for invoice items
            document.getElementById('invoiceItems').addEventListener('input', calculateInvoiceTotals);
            document.getElementById('billItems').addEventListener('input', calculateBillTotals);
            
            // Load any saved settings
            loadSettings();
            
            // Initialize new features
            setupRealTimeUpdates();
            setupKeyboardShortcuts();
            
            // Render initial data
            renderAllData();
            updateDashboard();
            updateRecentActivity();
            renderChat();
            renderReportChat();
            
            // Add initial invoice and bill items
            addInvoiceItem();
            addBillItem();
            
            // Check if we need sample data
            if (invoices.length === 0 && bills.length === 0) {
                setTimeout(() => {
                    if (confirm('Would you like to generate sample data to see how the app works?')) {
                        generateSampleData();
                    }
                }, 1000);
            }
        });

        // Navigation function
        function navigateToTab(tabId) {
            // Remove active class from all nav items
            document.querySelectorAll('.nav-item').forEach(nav => {
                nav.classList.remove('active');
            });
            
            // Add active class to target nav item
            document.querySelector(`[data-tab="${tabId}"]`).classList.add('active');
            
            // Hide all tab contents
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Show selected tab content
            document.getElementById(tabId).classList.add('active');
        }

        // Fix for invoice and bill creation
        function showInvoiceForm(invoiceId = null) {
            // Generate next invoice number or use existing
            if (invoiceId) {
                // Editing existing invoice
                const invoice = invoices.find(inv => inv.id === invoiceId);
                if (invoice) {
                    document.getElementById('invoiceModalTitle').textContent = 'Edit Invoice';
                    document.getElementById('invoiceId').value = invoice.id;
                    document.getElementById('invoiceNumber').value = invoice.number;
                    document.getElementById('invoiceDate').value = invoice.date;
                    document.getElementById('invoiceDueDate').value = invoice.dueDate;
                    document.getElementById('invoiceClient').value = invoice.clientId;
                    document.getElementById('invoiceNotes').value = invoice.notes || '';
                    
                    // Clear existing items
                    document.getElementById('invoiceItems').innerHTML = '';
                    
                    // Add items
                    invoice.items.forEach(item => {
                        addInvoiceItem();
                        const items = document.querySelectorAll('.invoice-item');
                        const lastItem = items[items.length - 1];
                        lastItem.querySelector('input[type="text"]').value = item.description;
                        lastItem.querySelector('input[type="number"]:nth-child(2)').value = item.quantity;
                        lastItem.querySelector('input[type="number"]:nth-child(3)').value = item.price;
                    });
                    
                    calculateInvoiceTotals();
                }
            } else {
                // Creating new invoice
                document.getElementById('invoiceModalTitle').textContent = 'Create New Invoice';
                document.getElementById('invoiceId').value = '';
                const nextInvoiceNumber = invoices.length + 1;
                document.getElementById('invoiceNumber').value = `INV-${nextInvoiceNumber.toString().padStart(3, '0')}`;
                
                // Clear items and add one default
                document.getElementById('invoiceItems').innerHTML = '';
                addInvoiceItem();
                calculateInvoiceTotals();
            }
            
            // Populate client dropdown
            const clientSelect = document.getElementById('invoiceClient');
            clientSelect.innerHTML = '<option value="">Select Client</option>';
            customers.forEach(customer => {
                const option = document.createElement('option');
                option.value = customer.id;
                option.textContent = customer.name;
                clientSelect.appendChild(option);
            });
            
            showModal('invoiceModal');
        }

        function showBillForm(billId = null) {
            // Generate next bill number or use existing
            if (billId) {
                // Editing existing bill
                const bill = bills.find(b => b.id === billId);
                if (bill) {
                    document.getElementById('billModalTitle').textContent = 'Edit Bill';
                    document.getElementById('billId').value = bill.id;
                    document.getElementById('billNumber').value = bill.number;
                    document.getElementById('billDate').value = bill.date;
                    document.getElementById('billDueDate').value = bill.dueDate;
                    document.getElementById('billVendor').value = bill.vendorId;
                    document.getElementById('billNotes').value = bill.notes || '';
                    
                    // Clear existing items
                    document.getElementById('billItems').innerHTML = '';
                    
                    // Add items
                    bill.items.forEach(item => {
                        addBillItem();
                        const items = document.querySelectorAll('.bill-item');
                        const lastItem = items[items.length - 1];
                        lastItem.querySelector('input[type="text"]').value = item.description;
                        lastItem.querySelector('input[type="number"]:nth-child(2)').value = item.quantity;
                        lastItem.querySelector('input[type="number"]:nth-child(3)').value = item.price;
                    });
                    
                    calculateBillTotals();
                }
            } else {
                // Creating new bill
                document.getElementById('billModalTitle').textContent = 'Create New Bill';
                document.getElementById('billId').value = '';
                const nextBillNumber = bills.length + 1;
                document.getElementById('billNumber').value = `BL-${nextBillNumber.toString().padStart(3, '0')}`;
                
                // Clear items and add one default
                document.getElementById('billItems').innerHTML = '';
                addBillItem();
                calculateBillTotals();
            }
            
            // Populate vendor dropdown
            const vendorSelect = document.getElementById('billVendor');
            vendorSelect.innerHTML = '<option value="">Select Vendor</option>';
            vendors.forEach(vendor => {
                const option = document.createElement('option');
                option.value = vendor.id;
                option.textContent = vendor.name;
                vendorSelect.appendChild(option);
            });
            
            showModal('billModal');
        }

        // Show forms for other entities
        function showInventoryForm(inventoryId = null) {
            if (inventoryId) {
                const item = inventory.find(i => i.id === inventoryId);
                if (item) {
                    document.getElementById('inventoryModalTitle').textContent = 'Edit Inventory Item';
                    document.getElementById('inventoryId').value = item.id;
                    document.getElementById('inventoryName').value = item.name;
                    document.getElementById('inventorySku').value = item.sku;
                    document.getElementById('inventoryCategory').value = item.category;
                    document.getElementById('inventoryQuantity').value = item.quantity;
                    document.getElementById('inventoryPrice').value = item.price;
                    document.getElementById('inventoryDescription').value = item.description || '';
                }
            } else {
                document.getElementById('inventoryModalTitle').textContent = 'Add Inventory Item';
                document.getElementById('inventoryId').value = '';
                document.getElementById('inventoryName').value = '';
                document.getElementById('inventorySku').value = '';
                document.getElementById('inventoryCategory').value = '';
                document.getElementById('inventoryQuantity').value = 0;
                document.getElementById('inventoryPrice').value = 0;
                document.getElementById('inventoryDescription').value = '';
            }
            
            // Populate category dropdown
            const categorySelect = document.getElementById('inventoryCategory');
            categorySelect.innerHTML = '<option value="">Select Category</option>';
            categories.filter(c => c.type === 'inventory').forEach(category => {
                const option = document.createElement('option');
                option.value = category.id;
                option.textContent = category.name;
                categorySelect.appendChild(option);
            });
            
            showModal('inventoryModal');
        }

        function showEmployeeForm(employeeId = null) {
            if (employeeId) {
                const employee = employees.find(e => e.id === employeeId);
                if (employee) {
                    document.getElementById('employeeModalTitle').textContent = 'Edit Employee';
                    document.getElementById('employeeId').value = employee.id;
                    document.getElementById('employeeName').value = employee.name;
                    document.getElementById('employeePosition').value = employee.position;
                    document.getElementById('employeeDepartment').value = employee.department;
                    document.getElementById('employeeEmail').value = employee.email;
                    document.getElementById('employeePhone').value = employee.phone;
                    document.getElementById('employeeSalary').value = employee.salary;
                    document.getElementById('employeeStatus').value = employee.status;
                }
            } else {
                document.getElementById('employeeModalTitle').textContent = 'Add Employee';
                document.getElementById('employeeId').value = '';
                document.getElementById('employeeName').value = '';
                document.getElementById('employeePosition').value = '';
                document.getElementById('employeeDepartment').value = '';
                document.getElementById('employeeEmail').value = '';
                document.getElementById('employeePhone').value = '';
                document.getElementById('employeeSalary').value = 0;
                document.getElementById('employeeStatus').value = 'active';
            }
            
            showModal('employeeModal');
        }

        function showCustomerForm(customerId = null) {
            if (customerId) {
                const customer = customers.find(c => c.id === customerId);
                if (customer) {
                    document.getElementById('customerModalTitle').textContent = 'Edit Customer';
                    document.getElementById('customerId').value = customer.id;
                    document.getElementById('customerName').value = customer.name;
                    document.getElementById('customerEmail').value = customer.email;
                    document.getElementById('customerPhone').value = customer.phone;
                    document.getElementById('customerCompany').value = customer.company || '';
                    document.getElementById('customerAddress').value = customer.address || '';
                }
            } else {
                document.getElementById('customerModalTitle').textContent = 'Add Customer';
                document.getElementById('customerId').value = '';
                document.getElementById('customerName').value = '';
                document.getElementById('customerEmail').value = '';
                document.getElementById('customerPhone').value = '';
                document.getElementById('customerCompany').value = '';
                document.getElementById('customerAddress').value = '';
            }
            
            showModal('customerModal');
        }

        function showVendorForm(vendorId = null) {
            if (vendorId) {
                const vendor = vendors.find(v => v.id === vendorId);
                if (vendor) {
                    document.getElementById('vendorModalTitle').textContent = 'Edit Vendor';
                    document.getElementById('vendorId').value = vendor.id;
                    document.getElementById('vendorName').value = vendor.name;
                    document.getElementById('vendorEmail').value = vendor.email;
                    document.getElementById('vendorPhone').value = vendor.phone;
                    document.getElementById('vendorCategory').value = vendor.category;
                    document.getElementById('vendorAddress').value = vendor.address || '';
                }
            } else {
                document.getElementById('vendorModalTitle').textContent = 'Add Vendor';
                document.getElementById('vendorId').value = '';
                document.getElementById('vendorName').value = '';
                document.getElementById('vendorEmail').value = '';
                document.getElementById('vendorPhone').value = '';
                document.getElementById('vendorCategory').value = '';
                document.getElementById('vendorAddress').value = '';
            }
            
            showModal('vendorModal');
        }

        function showCategoryForm(categoryId = null) {
            if (categoryId) {
                const category = categories.find(c => c.id === categoryId);
                if (category) {
                    document.getElementById('categoryModalTitle').textContent = 'Edit Category';
                    document.getElementById('categoryId').value = category.id;
                    document.getElementById('categoryName').value = category.name;
                    document.getElementById('categoryType').value = category.type;
                    document.getElementById('categoryDescription').value = category.description || '';
                }
            } else {
                document.getElementById('categoryModalTitle').textContent = 'Add Category';
                document.getElementById('categoryId').value = '';
                document.getElementById('categoryName').value = '';
                document.getElementById('categoryType').value = 'expense';
                document.getElementById('categoryDescription').value = '';
            }
            
            showModal('categoryModal');
        }

        function showTransactionForm(transactionId = null) {
            if (transactionId) {
                const transaction = transactions.find(t => t.id === transactionId);
                if (transaction) {
                    document.getElementById('transactionModalTitle').textContent = 'Edit Transaction';
                    document.getElementById('transactionId').value = transaction.id;
                    document.getElementById('transactionDate').value = transaction.date;
                    document.getElementById('transactionDescription').value = transaction.description;
                    document.getElementById('transactionType').value = transaction.type;
                    document.getElementById('transactionCategory').value = transaction.category;
                    document.getElementById('transactionAmount').value = Math.abs(transaction.amount);
                    document.getElementById('transactionNotes').value = transaction.notes || '';
                }
            } else {
                document.getElementById('transactionModalTitle').textContent = 'Add Transaction';
                document.getElementById('transactionId').value = '';
                document.getElementById('transactionDate').value = new Date().toISOString().split('T')[0];
                document.getElementById('transactionDescription').value = '';
                document.getElementById('transactionType').value = 'expense';
                document.getElementById('transactionCategory').value = '';
                document.getElementById('transactionAmount').value = 0;
                document.getElementById('transactionNotes').value = '';
            }
            
            // Populate category dropdown
            const categorySelect = document.getElementById('transactionCategory');
            categorySelect.innerHTML = '<option value="">Select Category</option>';
            categories.forEach(category => {
                const option = document.createElement('option');
                option.value = category.id;
                option.textContent = category.name;
                categorySelect.appendChild(option);
            });
            
            showModal('transactionModal');
        }

        function showTaxRuleForm(taxRuleId = null) {
            if (taxRuleId) {
                const taxRule = taxRules.find(t => t.id === taxRuleId);
                if (taxRule) {
                    document.getElementById('taxRuleModalTitle').textContent = 'Edit Tax Rule';
                    document.getElementById('taxRuleId').value = taxRule.id;
                    document.getElementById('taxRuleName').value = taxRule.name;
                    document.getElementById('taxRuleRate').value = taxRule.rate;
                    document.getElementById('taxRuleType').value = taxRule.type;
                    document.getElementById('taxRuleApplicable').value = taxRule.applicable;
                }
            } else {
                document.getElementById('taxRuleModalTitle').textContent = 'Add Tax Rule';
                document.getElementById('taxRuleId').value = '';
                document.getElementById('taxRuleName').value = '';
                document.getElementById('taxRuleRate').value = 0;
                document.getElementById('taxRuleType').value = 'vat';
                document.getElementById('taxRuleApplicable').value = 'all';
            }
            
            showModal('taxRuleModal');
        }

        // Fix for invoice and bill form submissions
        function handleInvoiceSubmit(e) {
            e.preventDefault();
            
            // Collect form data
            const items = [];
            document.querySelectorAll('.invoice-item').forEach(item => {
                const description = item.querySelector('input[type="text"]').value;
                const quantity = parseFloat(item.querySelector('input[type="number"]:nth-child(2)').value) || 0;
                const price = parseFloat(item.querySelector('input[type="number"]:nth-child(3)').value) || 0;
                if (description && quantity > 0 && price >= 0) {
                    items.push({ description, quantity, price, total: quantity * price });
                }
            });
            
            if (items.length === 0) {
                showToast('Please add at least one valid item', 'error');
                return;
            }
            
            const subtotal = items.reduce((sum, item) => sum + item.total, 0);
            const vatAmount = parseFloat(document.getElementById('invoiceVat').value) || 0;
            const total = subtotal + vatAmount;
            
            const clientSelect = document.getElementById('invoiceClient');
            const clientName = clientSelect.options[clientSelect.selectedIndex].text;
            
            const invoiceData = {
                number: document.getElementById('invoiceNumber').value,
                date: document.getElementById('invoiceDate').value,
                dueDate: document.getElementById('invoiceDueDate').value,
                clientId: document.getElementById('invoiceClient').value,
                clientName: clientName,
                items: items,
                subtotal: subtotal,
                vat: vatAmount,
                total: total,
                notes: document.getElementById('invoiceNotes').value,
                status: 'pending'
            };
            
            const invoiceId = document.getElementById('invoiceId').value;
            if (invoiceId) {
                // Update existing invoice
                const index = invoices.findIndex(inv => inv.id === invoiceId);
                if (index !== -1) {
                    invoices[index] = { ...invoices[index], ...invoiceData };
                    showToast('Invoice updated successfully!', 'success');
                    addRecentActivity(`Updated invoice ${invoiceData.number}`);
                }
            } else {
                // Create new invoice
                const invoice = {
                    id: Date.now().toString(),
                    ...invoiceData,
                    createdAt: new Date().toISOString()
                };
                invoices.push(invoice);
                showToast('Invoice created successfully!', 'success');
                addRecentActivity(`Created invoice ${invoice.number} for ${invoice.clientName}`);
                
                // Add to transactions
                transactions.push({
                    id: Date.now().toString(),
                    date: invoice.date,
                    description: `Invoice ${invoice.number}`,
                    type: 'invoice',
                    amount: invoice.total,
                    category: 'income',
                    createdAt: new Date().toISOString()
                });
            }
            
            saveToLocalStorage();
            renderInvoices();
            updateDashboard();
            updateRecentActivity();
            closeModal('invoiceModal');
        }

        function handleBillSubmit(e) {
            e.preventDefault();
            
            // Collect form data
            const items = [];
            document.querySelectorAll('.bill-item').forEach(item => {
                const description = item.querySelector('input[type="text"]').value;
                const quantity = parseFloat(item.querySelector('input[type="number"]:nth-child(2)').value) || 0;
                const price = parseFloat(item.querySelector('input[type="number"]:nth-child(3)').value) || 0;
                if (description && quantity > 0 && price >= 0) {
                    items.push({ description, quantity, price, total: quantity * price });
                }
            });
            
            if (items.length === 0) {
                showToast('Please add at least one valid item', 'error');
                return;
            }
            
            const subtotal = items.reduce((sum, item) => sum + item.total, 0);
            const vatAmount = parseFloat(document.getElementById('billVat').value) || 0;
            const total = subtotal + vatAmount;
            
            const vendorSelect = document.getElementById('billVendor');
            const vendorName = vendorSelect.options[vendorSelect.selectedIndex].text;
            
            const billData = {
                number: document.getElementById('billNumber').value,
                date: document.getElementById('billDate').value,
                dueDate: document.getElementById('billDueDate').value,
                vendorId: document.getElementById('billVendor').value,
                vendorName: vendorName,
                items: items,
                subtotal: subtotal,
                vat: vatAmount,
                total: total,
                notes: document.getElementById('billNotes').value,
                status: 'pending'
            };
            
            const billId = document.getElementById('billId').value;
            if (billId) {
                // Update existing bill
                const index = bills.findIndex(b => b.id === billId);
                if (index !== -1) {
                    bills[index] = { ...bills[index], ...billData };
                    showToast('Bill updated successfully!', 'success');
                    addRecentActivity(`Updated bill ${billData.number}`);
                }
            } else {
                // Create new bill
                const bill = {
                    id: Date.now().toString(),
                    ...billData,
                    createdAt: new Date().toISOString()
                };
                bills.push(bill);
                showToast('Bill created successfully!', 'success');
                addRecentActivity(`Created bill ${bill.number} for ${bill.vendorName}`);
                
                // Add to transactions
                transactions.push({
                    id: Date.now().toString(),
                    date: bill.date,
                    description: `Bill ${bill.number}`,
                    type: 'bill',
                    amount: -bill.total,
                    category: 'expense',
                    createdAt: new Date().toISOString()
                });
            }
            
            saveToLocalStorage();
            renderBills();
            updateDashboard();
            updateRecentActivity();
            closeModal('billModal');
        }

        // Form submission handlers for other entities
        function handleInventorySubmit(e) {
            e.preventDefault();
            
            const inventoryData = {
                name: document.getElementById('inventoryName').value,
                sku: document.getElementById('inventorySku').value,
                category: document.getElementById('inventoryCategory').value,
                quantity: parseFloat(document.getElementById('inventoryQuantity').value) || 0,
                price: parseFloat(document.getElementById('inventoryPrice').value) || 0,
                description: document.getElementById('inventoryDescription').value
            };
            
            const inventoryId = document.getElementById('inventoryId').value;
            if (inventoryId) {
                const index = inventory.findIndex(i => i.id === inventoryId);
                if (index !== -1) {
                    inventory[index] = { ...inventory[index], ...inventoryData };
                    showToast('Inventory item updated successfully!', 'success');
                }
            } else {
                const item = {
                    id: Date.now().toString(),
                    ...inventoryData,
                    status: inventoryData.quantity > 10 ? 'in-stock' : inventoryData.quantity > 0 ? 'low-stock' : 'out-of-stock',
                    createdAt: new Date().toISOString()
                };
                inventory.push(item);
                showToast('Inventory item added successfully!', 'success');
                addRecentActivity(`Added inventory item ${item.name}`);
            }
            
            saveToLocalStorage();
            renderInventory();
            updateDashboard();
            updateRecentActivity();
            closeModal('inventoryModal');
        }

        function handleEmployeeSubmit(e) {
            e.preventDefault();
            
            const employeeData = {
                name: document.getElementById('employeeName').value,
                position: document.getElementById('employeePosition').value,
                department: document.getElementById('employeeDepartment').value,
                email: document.getElementById('employeeEmail').value,
                phone: document.getElementById('employeePhone').value,
                salary: parseFloat(document.getElementById('employeeSalary').value) || 0,
                status: document.getElementById('employeeStatus').value
            };
            
            const employeeId = document.getElementById('employeeId').value;
            if (employeeId) {
                const index = employees.findIndex(emp => emp.id === employeeId);
                if (index !== -1) {
                    employees[index] = { ...employees[index], ...employeeData };
                    showToast('Employee updated successfully!', 'success');
                }
            } else {
                const employee = {
                    id: Date.now().toString(),
                    ...employeeData,
                    createdAt: new Date().toISOString()
                };
                employees.push(employee);
                showToast('Employee added successfully!', 'success');
                addRecentActivity(`Added employee ${employee.name}`);
            }
            
            saveToLocalStorage();
            renderEmployees();
            updateDashboard();
            updateRecentActivity();
            closeModal('employeeModal');
        }

        function handleCustomerSubmit(e) {
            e.preventDefault();
            
            const customerData = {
                name: document.getElementById('customerName').value,
                email: document.getElementById('customerEmail').value,
                phone: document.getElementById('customerPhone').value,
                company: document.getElementById('customerCompany').value,
                address: document.getElementById('customerAddress').value
            };
            
            const customerId = document.getElementById('customerId').value;
            if (customerId) {
                const index = customers.findIndex(c => c.id === customerId);
                if (index !== -1) {
                    customers[index] = { ...customers[index], ...customerData };
                    showToast('Customer updated successfully!', 'success');
                }
            } else {
                const customer = {
                    id: Date.now().toString(),
                    ...customerData,
                    totalSpent: 0,
                    createdAt: new Date().toISOString()
                };
                customers.push(customer);
                showToast('Customer added successfully!', 'success');
                addRecentActivity(`Added customer ${customer.name}`);
            }
            
            saveToLocalStorage();
            renderCustomers();
            updateDashboard();
            updateRecentActivity();
            closeModal('customerModal');
        }

        function handleVendorSubmit(e) {
            e.preventDefault();
            
            const vendorData = {
                name: document.getElementById('vendorName').value,
                email: document.getElementById('vendorEmail').value,
                phone: document.getElementById('vendorPhone').value,
                category: document.getElementById('vendorCategory').value,
                address: document.getElementById('vendorAddress').value
            };
            
            const vendorId = document.getElementById('vendorId').value;
            if (vendorId) {
                const index = vendors.findIndex(v => v.id === vendorId);
                if (index !== -1) {
                    vendors[index] = { ...vendors[index], ...vendorData };
                    showToast('Vendor updated successfully!', 'success');
                }
            } else {
                const vendor = {
                    id: Date.now().toString(),
                    ...vendorData,
                    totalBilled: 0,
                    createdAt: new Date().toISOString()
                };
                vendors.push(vendor);
                showToast('Vendor added successfully!', 'success');
                addRecentActivity(`Added vendor ${vendor.name}`);
            }
            
            saveToLocalStorage();
            renderVendors();
            updateDashboard();
            updateRecentActivity();
            closeModal('vendorModal');
        }

        function handleCategorySubmit(e) {
            e.preventDefault();
            
            const categoryData = {
                name: document.getElementById('categoryName').value,
                type: document.getElementById('categoryType').value,
                description: document.getElementById('categoryDescription').value
            };
            
            const categoryId = document.getElementById('categoryId').value;
            if (categoryId) {
                const index = categories.findIndex(c => c.id === categoryId);
                if (index !== -1) {
                    categories[index] = { ...categories[index], ...categoryData };
                    showToast('Category updated successfully!', 'success');
                }
            } else {
                const category = {
                    id: Date.now().toString(),
                    ...categoryData,
                    itemCount: 0,
                    createdAt: new Date().toISOString()
                };
                categories.push(category);
                showToast('Category added successfully!', 'success');
                addRecentActivity(`Added category ${category.name}`);
            }
            
            saveToLocalStorage();
            renderCategories();
            updateDashboard();
            updateRecentActivity();
            closeModal('categoryModal');
        }

        function handleTransactionSubmit(e) {
            e.preventDefault();
            
            const amount = parseFloat(document.getElementById('transactionAmount').value) || 0;
            const type = document.getElementById('transactionType').value;
            
            const transactionData = {
                date: document.getElementById('transactionDate').value,
                description: document.getElementById('transactionDescription').value,
                type: type,
                category: document.getElementById('transactionCategory').value,
                amount: type === 'income' ? amount : -amount,
                notes: document.getElementById('transactionNotes').value
            };
            
            const transactionId = document.getElementById('transactionId').value;
            if (transactionId) {
                const index = transactions.findIndex(t => t.id === transactionId);
                if (index !== -1) {
                    transactions[index] = { ...transactions[index], ...transactionData };
                    showToast('Transaction updated successfully!', 'success');
                }
            } else {
                const transaction = {
                    id: Date.now().toString(),
                    ...transactionData,
                    createdAt: new Date().toISOString()
                };
                transactions.push(transaction);
                showToast('Transaction added successfully!', 'success');
                addRecentActivity(`Added ${type} transaction: ${transaction.description}`);
            }
            
            saveToLocalStorage();
            renderTransactions();
            updateDashboard();
            updateRecentActivity();
            closeModal('transactionModal');
        }

        function handleTaxRuleSubmit(e) {
            e.preventDefault();
            
            const taxRuleData = {
                name: document.getElementById('taxRuleName').value,
                rate: parseFloat(document.getElementById('taxRuleRate').value) || 0,
                type: document.getElementById('taxRuleType').value,
                applicable: document.getElementById('taxRuleApplicable').value
            };
            
            const taxRuleId = document.getElementById('taxRuleId').value;
            if (taxRuleId) {
                const index = taxRules.findIndex(t => t.id === taxRuleId);
                if (index !== -1) {
                    taxRules[index] = { ...taxRules[index], ...taxRuleData };
                    showToast('Tax rule updated successfully!', 'success');
                }
            } else {
                const taxRule = {
                    id: Date.now().toString(),
                    ...taxRuleData,
                    createdAt: new Date().toISOString()
                };
                taxRules.push(taxRule);
                showToast('Tax rule added successfully!', 'success');
                addRecentActivity(`Added tax rule: ${taxRule.name}`);
            }
            
            saveToLocalStorage();
            renderTaxRules();
            updateDashboard();
            updateRecentActivity();
            closeModal('taxRuleModal');
        }

        // Chat Functions
        function sendMessage() {
            const input = document.getElementById('chatInput');
            const message = input.value.trim();
            
            if (message) {
                chatMessages.push({ sender: 'user', message });
                renderChat();
                
                // Simulate system response
                setTimeout(() => {
                    const responses = [
                        "I understand you're asking about " + message + ". How can I assist you further?",
                        "Thank you for your message. Is there anything specific you'd like help with?",
                        "I've noted your query about " + message + ". Our support team can provide more detailed assistance if needed.",
                        "That's an interesting question about " + message + ". Let me know if you need more information."
                    ];
                    const response = responses[Math.floor(Math.random() * responses.length)];
                    chatMessages.push({ sender: 'system', message: response });
                    renderChat();
                }, 1000);
                
                input.value = '';
            }
        }

        function sendReportMessage() {
            const input = document.getElementById('reportChatInput');
            const message = input.value.trim();
            
            if (message) {
                reportChatMessages.push({ sender: 'user', message });
                renderReportChat();
                
                // Simulate report assistant response
                setTimeout(() => {
                    let response = "";
                    if (message.toLowerCase().includes('sales') || message.toLowerCase().includes('revenue')) {
                        const totalSales = invoices.filter(inv => inv.status === 'paid')
                            .reduce((sum, inv) => sum + inv.total, 0);
                        response = `Your total sales are KSh ${totalSales.toFixed(2)}. Would you like to see a detailed sales report?`;
                    } else if (message.toLowerCase().includes('expense') || message.toLowerCase().includes('bill')) {
                        const totalBills = bills.filter(bill => bill.status === 'paid')
                            .reduce((sum, bill) => sum + bill.total, 0);
                        response = `Your total expenses are KSh ${totalBills.toFixed(2)}. I can help you analyze your spending patterns.`;
                    } else if (message.toLowerCase().includes('profit') || message.toLowerCase().includes('net')) {
                        const income = transactions.filter(t => t.category === 'income')
                            .reduce((sum, t) => sum + t.amount, 0);
                        const expenses = transactions.filter(t => t.category === 'expense')
                            .reduce((sum, t) => sum + t.amount, 0);
                        const profit = income - expenses;
                        response = `Your net profit is KSh ${profit.toFixed(2)}. Would you like to see a breakdown?`;
                    } else {
                        response = "I can help you with sales reports, expense analysis, profit calculations, and more. What specific report would you like to see?";
                    }
                    
                    reportChatMessages.push({ sender: 'system', message: response });
                    renderReportChat();
                }, 1000);
                
                input.value = '';
            }
        }

        function handleChatKeypress(e) {
            if (e.key === 'Enter') {
                sendMessage();
            }
        }

        function handleReportChatKeypress(e) {
            if (e.key === 'Enter') {
                sendReportMessage();
            }
        }

        function renderChat() {
            const chatMessagesElement = document.getElementById('chatMessages');
            chatMessagesElement.innerHTML = '';
            
            chatMessages.forEach(msg => {
                const messageDiv = document.createElement('div');
                messageDiv.className = `message ${msg.sender}`;
                messageDiv.innerHTML = `<strong>${msg.sender === 'user' ? 'You' : 'System'}:</strong> ${msg.message}`;
                chatMessagesElement.appendChild(messageDiv);
            });
            
            chatMessagesElement.scrollTop = chatMessagesElement.scrollHeight;
        }

        function renderReportChat() {
            const chatMessagesElement = document.getElementById('reportChatMessages');
            chatMessagesElement.innerHTML = '';
            
            reportChatMessages.forEach(msg => {
                const messageDiv = document.createElement('div');
                messageDiv.className = `message ${msg.sender}`;
                messageDiv.innerHTML = `<strong>${msg.sender === 'user' ? 'You' : 'Assistant'}:</strong> ${msg.message}`;
                chatMessagesElement.appendChild(messageDiv);
            });
            
            chatMessagesElement.scrollTop = chatMessagesElement.scrollHeight;
        }

        function clearChat() {
            chatMessages = [
                { sender: 'system', message: 'Welcome to The Record Book! How can I help you today?' }
            ];
            renderChat();
        }

        // Utility Functions
        function showModal(modalId) {
            document.getElementById(modalId).style.display = 'flex';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }

        function saveToLocalStorage() {
            const data = {
                invoices, bills, inventory, employees, customers, vendors, categories, transactions, taxRules, settings
            };
            localStorage.setItem('recordBookData', JSON.stringify(data));
        }

        function loadFromLocalStorage() {
            const savedData = localStorage.getItem('recordBookData');
            if (savedData) {
                const data = JSON.parse(savedData);
                invoices = data.invoices || [];
                bills = data.bills || [];
                inventory = data.inventory || [];
                employees = data.employees || [];
                customers = data.customers || [];
                vendors = data.vendors || [];
                categories = data.categories || [];
                transactions = data.transactions || [];
                taxRules = data.taxRules || [];
                settings = data.settings || {};
            }
        }

        function showToast(message, type = 'success') {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.className = `toast ${type}`;
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        function addInvoiceItem() {
            const itemsContainer = document.getElementById('invoiceItems');
            const newItem = document.createElement('div');
            newItem.className = 'form-row invoice-item';
            newItem.innerHTML = `
                <div class="form-group">
                    <input type="text" placeholder="Item Description" required>
                </div>
                <div class="form-group">
                    <input type="number" placeholder="Quantity" min="1" value="1" required>
                </div>
                <div class="form-group">
                    <input type="number" placeholder="Price" min="0" step="0.01" value="0" required>
                </div>
                <div class="form-group">
                    <button type="button" class="btn-danger" onclick="removeInvoiceItem(this)"><i class="fas fa-trash"></i></button>
                </div>
            `;
            itemsContainer.appendChild(newItem);
            
            // Add event listeners to new inputs
            newItem.querySelectorAll('input').forEach(input => {
                input.addEventListener('input', calculateInvoiceTotals);
            });
        }

        function removeInvoiceItem(button) {
            const item = button.closest('.invoice-item');
            if (document.querySelectorAll('.invoice-item').length > 1) {
                item.remove();
                calculateInvoiceTotals();
            }
        }

        function calculateInvoiceTotals() {
            let subtotal = 0;
            document.querySelectorAll('.invoice-item').forEach(item => {
                const quantity = parseFloat(item.querySelector('input[type="number"]:nth-child(2)').value) || 0;
                const price = parseFloat(item.querySelector('input[type="number"]:nth-child(3)').value) || 0;
                subtotal += quantity * price;
            });
            
            const vatRate = parseFloat(document.getElementById('settingsVatRate')?.value) || 0;
            const vatAmount = subtotal * (vatRate / 100);
            const total = subtotal + vatAmount;
            
            document.getElementById('invoiceVat').value = vatAmount.toFixed(2);
            document.getElementById('invoiceTotal').value = total.toFixed(2);
        }

        function addBillItem() {
            const itemsContainer = document.getElementById('billItems');
            const newItem = document.createElement('div');
            newItem.className = 'form-row bill-item';
            newItem.innerHTML = `
                <div class="form-group">
                    <input type="text" placeholder="Item Description" required>
                </div>
                <div class="form-group">
                    <input type="number" placeholder="Quantity" min="1" value="1" required>
                </div>
                <div class="form-group">
                    <input type="number" placeholder="Price" min="0" step="0.01" value="0" required>
                </div>
                <div class="form-group">
                    <button type="button" class="btn-danger" onclick="removeBillItem(this)"><i class="fas fa-trash"></i></button>
                </div>
            `;
            itemsContainer.appendChild(newItem);
            
            // Add event listeners to new inputs
            newItem.querySelectorAll('input').forEach(input => {
                input.addEventListener('input', calculateBillTotals);
            });
        }

        function removeBillItem(button) {
            const item = button.closest('.bill-item');
            if (document.querySelectorAll('.bill-item').length > 1) {
                item.remove();
                calculateBillTotals();
            }
        }

        function calculateBillTotals() {
            let subtotal = 0;
            document.querySelectorAll('.bill-item').forEach(item => {
                const quantity = parseFloat(item.querySelector('input[type="number"]:nth-child(2)').value) || 0;
                const price = parseFloat(item.querySelector('input[type="number"]:nth-child(3)').value) || 0;
                subtotal += quantity * price;
            });
            
            const vatRate = parseFloat(document.getElementById('settingsVatRate')?.value) || 0;
            const vatAmount = subtotal * (vatRate / 100);
            const total = subtotal + vatAmount;
            
            document.getElementById('billVat').value = vatAmount.toFixed(2);
            document.getElementById('billTotal').value = total.toFixed(2);
        }

        function renderAllData() {
            renderInvoices();
            renderBills();
            renderInventory();
            renderEmployees();
            renderCustomers();
            renderVendors();
            renderCategories();
            renderTransactions();
            renderTaxRules();
            updateClientAndVendorFilters();
        }

        function renderInvoices() {
            const tbody = document.getElementById('invoicesTableBody');
            const emptyState = document.getElementById('invoicesEmptyState');
            
            if (invoices.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = invoices.map(invoice => `
                <tr>
                    <td>${invoice.number}</td>
                    <td>${invoice.clientName}</td>
                    <td>${formatDate(invoice.date)}</td>
                    <td>${formatDate(invoice.dueDate)}</td>
                    <td>KSh ${invoice.total.toFixed(2)}</td>
                    <td><span class="status-badge ${invoice.status}">${invoice.status}</span></td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewInvoice('${invoice.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showInvoiceForm('${invoice.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('invoice', '${invoice.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderBills() {
            const tbody = document.getElementById('billsTableBody');
            const emptyState = document.getElementById('billsEmptyState');
            
            if (bills.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = bills.map(bill => `
                <tr>
                    <td>${bill.number}</td>
                    <td>${bill.vendorName}</td>
                    <td>${formatDate(bill.date)}</td>
                    <td>${formatDate(bill.dueDate)}</td>
                    <td>KSh ${bill.total.toFixed(2)}</td>
                    <td><span class="status-badge ${bill.status}">${bill.status}</span></td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewBill('${bill.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showBillForm('${bill.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('bill', '${bill.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderInventory() {
            const tbody = document.getElementById('inventoryTableBody');
            const emptyState = document.getElementById('inventoryEmptyState');
            
            if (inventory.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = inventory.map(item => `
                <tr>
                    <td>${item.name}</td>
                    <td>${item.sku}</td>
                    <td>${item.category}</td>
                    <td>${item.quantity}</td>
                    <td>KSh ${item.price.toFixed(2)}</td>
                    <td><span class="status-badge ${item.status}">${item.status}</span></td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewInventory('${item.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showInventoryForm('${item.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('inventory', '${item.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderEmployees() {
            const tbody = document.getElementById('employeesTableBody');
            const emptyState = document.getElementById('employeesEmptyState');
            
            if (employees.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = employees.map(employee => `
                <tr>
                    <td>${employee.name}</td>
                    <td>${employee.position}</td>
                    <td>${employee.department}</td>
                    <td>${employee.email}</td>
                    <td>${employee.phone}</td>
                    <td><span class="status-badge ${employee.status}">${employee.status}</span></td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewEmployee('${employee.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showEmployeeForm('${employee.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('employee', '${employee.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderCustomers() {
            const tbody = document.getElementById('customersTableBody');
            const emptyState = document.getElementById('customersEmptyState');
            
            if (customers.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = customers.map(customer => `
                <tr>
                    <td>${customer.name}</td>
                    <td>${customer.email}</td>
                    <td>${customer.phone}</td>
                    <td>${customer.company || 'N/A'}</td>
                    <td>KSh ${customer.totalSpent.toFixed(2)}</td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewCustomer('${customer.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showCustomerForm('${customer.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('customer', '${customer.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderVendors() {
            const tbody = document.getElementById('vendorsTableBody');
            const emptyState = document.getElementById('vendorsEmptyState');
            
            if (vendors.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = vendors.map(vendor => `
                <tr>
                    <td>${vendor.name}</td>
                    <td>${vendor.email}</td>
                    <td>${vendor.phone}</td>
                    <td>${vendor.category}</td>
                    <td>KSh ${vendor.totalBilled.toFixed(2)}</td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewVendor('${vendor.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showVendorForm('${vendor.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('vendor', '${vendor.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderCategories() {
            const tbody = document.getElementById('categoriesTableBody');
            const emptyState = document.getElementById('categoriesEmptyState');
            
            if (categories.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = categories.map(category => `
                <tr>
                    <td>${category.name}</td>
                    <td>${category.type}</td>
                    <td>${category.description || 'N/A'}</td>
                    <td>${category.itemCount}</td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewCategory('${category.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showCategoryForm('${category.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('category', '${category.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderTransactions() {
            const tbody = document.getElementById('transactionsTableBody');
            const emptyState = document.getElementById('transactionsEmptyState');
            
            if (transactions.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            tbody.innerHTML = transactions.map(transaction => `
                <tr>
                    <td>${formatDate(transaction.date)}</td>
                    <td>${transaction.description}</td>
                    <td>${transaction.category}</td>
                    <td>${transaction.type}</td>
                    <td>KSh ${Math.abs(transaction.amount).toFixed(2)}</td>
                    <td class="action-buttons">
                        <button class="btn-primary action-btn" onclick="viewTransaction('${transaction.id}')"><i class="fas fa-eye"></i></button>
                        <button class="btn-warning action-btn" onclick="showTransactionForm('${transaction.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('transaction', '${transaction.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function renderTaxRules() {
            const tbody = document.getElementById('taxRulesTableBody');
            
            if (taxRules.length === 0) {
                tbody.innerHTML = '<tr><td colspan="5" class="text-center">No tax rules defined</td></tr>';
                return;
            }
            
            tbody.innerHTML = taxRules.map(rule => `
                <tr>
                    <td>${rule.name}</td>
                    <td>${rule.rate}%</td>
                    <td>${rule.type}</td>
                    <td>${rule.applicable}</td>
                    <td class="action-buttons">
                        <button class="btn-warning action-btn" onclick="showTaxRuleForm('${rule.id}')"><i class="fas fa-edit"></i></button>
                        <button class="btn-danger action-btn" onclick="confirmDelete('taxRule', '${rule.id}')"><i class="fas fa-trash"></i></button>
                    </td>
                </tr>
            `).join('');
        }

        function updateClientAndVendorFilters() {
            // Update client filter
            const clientFilter = document.getElementById('invoiceClientFilter');
            clientFilter.innerHTML = '<option value="all">All Clients</option>';
            const clients = [...new Set(invoices.map(inv => inv.clientName))];
            clients.forEach(client => {
                const option = document.createElement('option');
                option.value = client;
                option.textContent = client;
                clientFilter.appendChild(option);
            });
            
            // Update vendor filter
            const vendorFilter = document.getElementById('billVendorFilter');
            vendorFilter.innerHTML = '<option value="all">All Vendors</option>';
            const vendors = [...new Set(bills.map(bill => bill.vendorName))];
            vendors.forEach(vendor => {
                const option = document.createElement('option');
                option.value = vendor;
                option.textContent = vendor;
                vendorFilter.appendChild(option);
            });
        }

        function filterInvoices() {
            const searchTerm = document.getElementById('invoiceSearch').value.toLowerCase();
            const statusFilter = document.getElementById('invoiceStatusFilter').value;
            const clientFilter = document.getElementById('invoiceClientFilter').value;
            
            const filteredInvoices = invoices.filter(invoice => {
                const matchesSearch = invoice.number.toLowerCase().includes(searchTerm) || 
                                    invoice.clientName.toLowerCase().includes(searchTerm);
                const matchesStatus = statusFilter === 'all' || invoice.status === statusFilter;
                const matchesClient = clientFilter === 'all' || invoice.clientName === clientFilter;
                
                return matchesSearch && matchesStatus && matchesClient;
            });
            
            const tbody = document.getElementById('invoicesTableBody');
            const emptyState = document.getElementById('invoicesEmptyState');
            
            if (filteredInvoices.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredInvoices.map(invoice => `
                    <tr>
                        <td>${invoice.number}</td>
                        <td>${invoice.clientName}</td>
                        <td>${formatDate(invoice.date)}</td>
                        <td>${formatDate(invoice.dueDate)}</td>
                        <td>KSh ${invoice.total.toFixed(2)}</td>
                        <td><span class="status-badge ${invoice.status}">${invoice.status}</span></td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewInvoice('${invoice.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showInvoiceForm('${invoice.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('invoice', '${invoice.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterBills() {
            const searchTerm = document.getElementById('billsSearch').value.toLowerCase();
            const statusFilter = document.getElementById('billStatusFilter').value;
            const vendorFilter = document.getElementById('billVendorFilter').value;
            
            const filteredBills = bills.filter(bill => {
                const matchesSearch = bill.number.toLowerCase().includes(searchTerm) || 
                                    bill.vendorName.toLowerCase().includes(searchTerm);
                const matchesStatus = statusFilter === 'all' || bill.status === statusFilter;
                const matchesVendor = vendorFilter === 'all' || bill.vendorName === vendorFilter;
                
                return matchesSearch && matchesStatus && matchesVendor;
            });
            
            const tbody = document.getElementById('billsTableBody');
            const emptyState = document.getElementById('billsEmptyState');
            
            if (filteredBills.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredBills.map(bill => `
                    <tr>
                        <td>${bill.number}</td>
                        <td>${bill.vendorName}</td>
                        <td>${formatDate(bill.date)}</td>
                        <td>${formatDate(bill.dueDate)}</td>
                        <td>KSh ${bill.total.toFixed(2)}</td>
                        <td><span class="status-badge ${bill.status}">${bill.status}</span></td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewBill('${bill.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showBillForm('${bill.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('bill', '${bill.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterInventory() {
            const searchTerm = document.getElementById('inventorySearch').value.toLowerCase();
            const statusFilter = document.getElementById('inventoryStatusFilter').value;
            
            const filteredInventory = inventory.filter(item => {
                const matchesSearch = item.name.toLowerCase().includes(searchTerm) || 
                                    item.sku.toLowerCase().includes(searchTerm);
                const matchesStatus = statusFilter === 'all' || item.status === statusFilter;
                
                return matchesSearch && matchesStatus;
            });
            
            const tbody = document.getElementById('inventoryTableBody');
            const emptyState = document.getElementById('inventoryEmptyState');
            
            if (filteredInventory.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredInventory.map(item => `
                    <tr>
                        <td>${item.name}</td>
                        <td>${item.sku}</td>
                        <td>${item.category}</td>
                        <td>${item.quantity}</td>
                        <td>KSh ${item.price.toFixed(2)}</td>
                        <td><span class="status-badge ${item.status}">${item.status}</span></td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewInventory('${item.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showInventoryForm('${item.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('inventory', '${item.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterEmployees() {
            const searchTerm = document.getElementById('employeeSearch').value.toLowerCase();
            const statusFilter = document.getElementById('employeeStatusFilter').value;
            
            const filteredEmployees = employees.filter(employee => {
                const matchesSearch = employee.name.toLowerCase().includes(searchTerm) || 
                                    employee.position.toLowerCase().includes(searchTerm) ||
                                    employee.department.toLowerCase().includes(searchTerm);
                const matchesStatus = statusFilter === 'all' || employee.status === statusFilter;
                
                return matchesSearch && matchesStatus;
            });
            
            const tbody = document.getElementById('employeesTableBody');
            const emptyState = document.getElementById('employeesEmptyState');
            
            if (filteredEmployees.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredEmployees.map(employee => `
                    <tr>
                        <td>${employee.name}</td>
                        <td>${employee.position}</td>
                        <td>${employee.department}</td>
                        <td>${employee.email}</td>
                        <td>${employee.phone}</td>
                        <td><span class="status-badge ${employee.status}">${employee.status}</span></td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewEmployee('${employee.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showEmployeeForm('${employee.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('employee', '${employee.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterCustomers() {
            const searchTerm = document.getElementById('customerSearch').value.toLowerCase();
            
            const filteredCustomers = customers.filter(customer => {
                return customer.name.toLowerCase().includes(searchTerm) || 
                       customer.email.toLowerCase().includes(searchTerm) ||
                       customer.company.toLowerCase().includes(searchTerm);
            });
            
            const tbody = document.getElementById('customersTableBody');
            const emptyState = document.getElementById('customersEmptyState');
            
            if (filteredCustomers.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredCustomers.map(customer => `
                    <tr>
                        <td>${customer.name}</td>
                        <td>${customer.email}</td>
                        <td>${customer.phone}</td>
                        <td>${customer.company || 'N/A'}</td>
                        <td>KSh ${customer.totalSpent.toFixed(2)}</td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewCustomer('${customer.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showCustomerForm('${customer.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('customer', '${customer.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterVendors() {
            const searchTerm = document.getElementById('vendorSearch').value.toLowerCase();
            
            const filteredVendors = vendors.filter(vendor => {
                return vendor.name.toLowerCase().includes(searchTerm) || 
                       vendor.email.toLowerCase().includes(searchTerm) ||
                       vendor.category.toLowerCase().includes(searchTerm);
            });
            
            const tbody = document.getElementById('vendorsTableBody');
            const emptyState = document.getElementById('vendorsEmptyState');
            
            if (filteredVendors.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredVendors.map(vendor => `
                    <tr>
                        <td>${vendor.name}</td>
                        <td>${vendor.email}</td>
                        <td>${vendor.phone}</td>
                        <td>${vendor.category}</td>
                        <td>KSh ${vendor.totalBilled.toFixed(2)}</td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewVendor('${vendor.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showVendorForm('${vendor.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('vendor', '${vendor.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterCategories() {
            const searchTerm = document.getElementById('categorySearch').value.toLowerCase();
            
            const filteredCategories = categories.filter(category => {
                return category.name.toLowerCase().includes(searchTerm) || 
                       category.type.toLowerCase().includes(searchTerm);
            });
            
            const tbody = document.getElementById('categoriesTableBody');
            const emptyState = document.getElementById('categoriesEmptyState');
            
            if (filteredCategories.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredCategories.map(category => `
                    <tr>
                        <td>${category.name}</td>
                        <td>${category.type}</td>
                        <td>${category.description || 'N/A'}</td>
                        <td>${category.itemCount}</td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewCategory('${category.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showCategoryForm('${category.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('category', '${category.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function filterTransactions() {
            const searchTerm = document.getElementById('transactionSearch').value.toLowerCase();
            const typeFilter = document.getElementById('transactionTypeFilter').value;
            const categoryFilter = document.getElementById('transactionCategoryFilter').value;
            
            const filteredTransactions = transactions.filter(transaction => {
                const matchesSearch = transaction.description.toLowerCase().includes(searchTerm);
                const matchesType = typeFilter === 'all' || transaction.type === typeFilter;
                const matchesCategory = categoryFilter === 'all' || transaction.category === categoryFilter;
                
                return matchesSearch && matchesType && matchesCategory;
            });
            
            const tbody = document.getElementById('transactionsTableBody');
            const emptyState = document.getElementById('transactionsEmptyState');
            
            if (filteredTransactions.length === 0) {
                tbody.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                tbody.innerHTML = filteredTransactions.map(transaction => `
                    <tr>
                        <td>${formatDate(transaction.date)}</td>
                        <td>${transaction.description}</td>
                        <td>${transaction.category}</td>
                        <td>${transaction.type}</td>
                        <td>KSh ${Math.abs(transaction.amount).toFixed(2)}</td>
                        <td class="action-buttons">
                            <button class="btn-primary action-btn" onclick="viewTransaction('${transaction.id}')"><i class="fas fa-eye"></i></button>
                            <button class="btn-warning action-btn" onclick="showTransactionForm('${transaction.id}')"><i class="fas fa-edit"></i></button>
                            <button class="btn-danger action-btn" onclick="confirmDelete('transaction', '${transaction.id}')"><i class="fas fa-trash"></i></button>
                        </td>
                    </tr>
                `).join('');
            }
        }

        function updateDashboard() {
            // Update stats
            const totalSales = invoices.filter(inv => inv.status === 'paid')
                .reduce((sum, inv) => sum + inv.total, 0);
            document.getElementById('totalSales').textContent = `KSh ${totalSales.toFixed(2)}`;
            
            const pendingInvoices = invoices.filter(inv => inv.status === 'pending');
            document.getElementById('pendingInvoices').textContent = pendingInvoices.length;
            const pendingAmount = pendingInvoices.reduce((sum, inv) => sum + inv.total, 0);
            document.getElementById('pendingInvoicesAmount').textContent = `KSh ${pendingAmount.toFixed(2)}`;
            
            document.getElementById('inventoryItems').textContent = inventory.length;
            const lowStockCount = inventory.filter(item => item.status === 'low-stock').length;
            document.getElementById('lowStockItems').textContent = `${lowStockCount} Low Stock`;
            
            document.getElementById('totalEmployees').textContent = employees.length;
            const activeEmployees = employees.filter(emp => emp.status === 'active').length;
            document.getElementById('activeEmployees').textContent = `${activeEmployees} Active`;
            
            // Update recent transactions
            const recentTransactions = document.getElementById('recentTransactions');
            const transactionsEmptyState = document.getElementById('transactionsEmptyState');
            
            if (transactions.length === 0) {
                recentTransactions.innerHTML = '';
                transactionsEmptyState.style.display = 'block';
            } else {
                transactionsEmptyState.style.display = 'none';
                const recent = transactions.slice(-5).reverse();
                recentTransactions.innerHTML = recent.map(transaction => `
                    <tr>
                        <td>${formatDate(transaction.date)}</td>
                        <td>${transaction.description}</td>
                        <td>${transaction.type}</td>
                        <td>KSh ${Math.abs(transaction.amount).toFixed(2)}</td>
                        <td><span class="status-badge">${transaction.category}</span></td>
                    </tr>
                `).join('');
            }
        }

        function updateRecentActivity() {
            const recentActivity = document.getElementById('recentActivity');
            const emptyState = document.getElementById('recentActivityEmptyState');
            
            // Create some sample activities based on data
            const activities = [];
            
            if (invoices.length > 0) {
                const latestInvoice = invoices[invoices.length - 1];
                activities.push({
                    text: `Created invoice ${latestInvoice.number}`,
                    time: 'Just now'
                });
            }
            
            if (bills.length > 0) {
                const latestBill = bills[bills.length - 1];
                activities.push({
                    text: `Created bill ${latestBill.number}`,
                    time: 'Recently'
                });
            }
            
            if (activities.length === 0) {
                recentActivity.innerHTML = '';
                emptyState.style.display = 'block';
            } else {
                emptyState.style.display = 'none';
                recentActivity.innerHTML = activities.map(activity => `
                    <div style="padding: 8px; border-left: 3px solid var(--primary); background: var(--light);">
                        <div style="font-size: 0.8rem;">${activity.text}</div>
                        <div style="font-size: 0.7rem; color: var(--text-light);">${activity.time}</div>
                    </div>
                `).join('');
            }
        }

        function addRecentActivity(activityText) {
            // In a real app, you would add this to an activities array and save it
            updateRecentActivity();
        }

        function formatDate(dateString) {
            if (!dateString) return '';
            try {
                const date = new Date(dateString);
                if (isNaN(date.getTime())) return dateString; // Return original if invalid
                return date.toLocaleDateString('en-KE', {
                    year: 'numeric',
                    month: 'short',
                    day: 'numeric'
                });
            } catch (e) {
                return dateString;
            }
        }

        function setupRealTimeUpdates() {
            // Update dashboard every 30 seconds
            setInterval(() => {
                updateDashboard();
                updateRecentActivity();
            }, 30000);
        }

        function setupKeyboardShortcuts() {
            document.addEventListener('keydown', (e) => {
                if (e.ctrlKey || e.metaKey) {
                    const activeTab = document.querySelector('.nav-item.active'); // Declare once
                    switch(e.key) {
                        case 'n':
                            e.preventDefault();
                            if (activeTab) {
                                const tabName = activeTab.getAttribute('data-tab');
                                if (tabName === 'invoices') showInvoiceForm();
                                else if (tabName === 'bills') showBillForm();
                                else if (tabName === 'inventory') showInventoryForm();
                                else if (tabName === 'employees') showEmployeeForm();
                                else if (tabName === 'customers') showCustomerForm();
                                else if (tabName === 'vendors') showVendorForm();
                                else if (tabName === 'categories') showCategoryForm();
                                else if (tabName === 'transactions') showTransactionForm();
                            }
                            break;
                        case 's':
                            e.preventDefault();
                            saveToLocalStorage();
                            showToast('Data saved!', 'success');
                            break;
                        case 'f':
                            e.preventDefault();
                            if (activeTab) {
                                const tabName = activeTab.getAttribute('data-tab');
                                if (tabName === 'invoices') {
                                    document.getElementById('invoiceSearch').focus();
                                } else if (tabName === 'bills') {
                                    document.getElementById('billsSearch').focus();
                                } else if (tabName === 'inventory') {
                                    document.getElementById('inventorySearch').focus();
                                } else if (tabName === 'employees') {
                                    document.getElementById('employeeSearch').focus();
                                } else if (tabName === 'customers') {
                                    document.getElementById('customerSearch').focus();
                                } else if (tabName === 'vendors') {
                                    document.getElementById('vendorSearch').focus();
                                } else if (tabName === 'categories') {
                                    document.getElementById('categorySearch').focus();
                                } else if (tabName === 'transactions') {
                                    document.getElementById('transactionSearch').focus();
                                }
                            }
                            break;
                    }
                }
            });
        }

        function loadSettings() {
            const savedSettings = localStorage.getItem('recordBookSettings');
            if (savedSettings) {
                const settings = JSON.parse(savedSettings);
                if (document.getElementById('settingsVatRate')) {
                    document.getElementById('settingsVatRate').value = settings.vatRate || '';
                }
            }
        }

        // Delete functions
        function confirmDelete(type, id) {
            itemToDelete = { type, id };
            showModal('deleteModal');
        }

        function deleteItem() {
            if (itemToDelete) {
                const { type, id } = itemToDelete;
                
                if (type === 'invoice') {
                    invoices = invoices.filter(inv => inv.id !== id);
                    showToast('Invoice deleted successfully!', 'success');
                } else if (type === 'bill') {
                    bills = bills.filter(bill => bill.id !== id);
                    showToast('Bill deleted successfully!', 'success');
                } else if (type === 'inventory') {
                    inventory = inventory.filter(item => item.id !== id);
                    showToast('Inventory item deleted successfully!', 'success');
                } else if (type === 'employee') {
                    employees = employees.filter(emp => emp.id !== id);
                    showToast('Employee deleted successfully!', 'success');
                } else if (type === 'customer') {
                    customers = customers.filter(c => c.id !== id);
                    showToast('Customer deleted successfully!', 'success');
                } else if (type === 'vendor') {
                    vendors = vendors.filter(v => v.id !== id);
                    showToast('Vendor deleted successfully!', 'success');
                } else if (type === 'category') {
                    categories = categories.filter(c => c.id !== id);
                    showToast('Category deleted successfully!', 'success');
                } else if (type === 'transaction') {
                    transactions = transactions.filter(t => t.id !== id);
                    showToast('Transaction deleted successfully!', 'success');
                } else if (type === 'taxRule') {
                    taxRules = taxRules.filter(t => t.id !== id);
                    showToast('Tax rule deleted successfully!', 'success');
                }
                
                saveToLocalStorage();
                renderAllData();
                updateDashboard();
                updateRecentActivity();
                closeModal('deleteModal');
                itemToDelete = null;
            }
        }

        function deleteAllItems(type) {
            deleteAllType = type;
            document.getElementById('deleteAllType').textContent = type;
            showModal('deleteAllModal');
        }

        function proceedDeleteAll() {
            if (deleteAllType === 'invoices') {
                invoices = [];
                showToast('All invoices deleted!', 'success');
            } else if (deleteAllType === 'bills') {
                bills = [];
                showToast('All bills deleted!', 'success');
            } else if (deleteAllType === 'inventory') {
                inventory = [];
                showToast('All inventory items deleted!', 'success');
            } else if (deleteAllType === 'employees') {
                employees = [];
                showToast('All employees deleted!', 'success');
            } else if (deleteAllType === 'customers') {
                customers = [];
                showToast('All customers deleted!', 'success');
            } else if (deleteAllType === 'vendors') {
                vendors = [];
                showToast('All vendors deleted!', 'success');
            } else if (deleteAllType === 'categories') {
                categories = [];
                showToast('All categories deleted!', 'success');
            } else if (deleteAllType === 'transactions') {
                transactions = [];
                showToast('All transactions deleted!', 'success');
            }
            
            saveToLocalStorage();
            renderAllData();
            updateDashboard();
            updateRecentActivity();
            closeModal('deleteAllModal');
            deleteAllType = null;
        }

        // View details functions
        function viewInvoice(id) {
            const invoice = invoices.find(inv => inv.id === id);
            if (invoice) {
                let itemsHtml = '';
                invoice.items.forEach(item => {
                    itemsHtml += `${item.description}: ${item.quantity} x KSh ${item.price.toFixed(2)} = KSh ${item.total.toFixed(2)}\n`;
                });
                
                const details = `
Invoice Details:
Number: ${invoice.number}
Client: ${invoice.clientName}
Date: ${formatDate(invoice.date)}
Due Date: ${formatDate(invoice.dueDate)}
Status: ${invoice.status}

Items:
${itemsHtml}
Subtotal: KSh ${invoice.subtotal.toFixed(2)}
VAT: KSh ${invoice.vat.toFixed(2)}
Total: KSh ${invoice.total.toFixed(2)}
${invoice.notes ? `Notes: ${invoice.notes}` : ''}
                `;
                alert(details);
            }
        }

        function viewBill(id) {
            const bill = bills.find(b => b.id === id);
            if (bill) {
                let itemsHtml = '';
                bill.items.forEach(item => {
                    itemsHtml += `${item.description}: ${item.quantity} x KSh ${item.price.toFixed(2)} = KSh ${item.total.toFixed(2)}\n`;
                });
                
                const details = `
Bill Details:
Number: ${bill.number}
Vendor: ${bill.vendorName}
Date: ${formatDate(bill.date)}
Due Date: ${formatDate(bill.dueDate)}
Status: ${bill.status}

Items:
${itemsHtml}
Subtotal: KSh ${bill.subtotal.toFixed(2)}
VAT: KSh ${bill.vat.toFixed(2)}
Total: KSh ${bill.total.toFixed(2)}
${bill.notes ? `Notes: ${bill.notes}` : ''}
                `;
                alert(details);
            }
        }

        function viewInventory(id) {
            const item = inventory.find(i => i.id === id);
            if (item) {
                const details = `
Inventory Item Details:
Name: ${item.name}
SKU: ${item.sku}
Category: ${item.category}
Quantity: ${item.quantity}
Price: KSh ${item.price.toFixed(2)}
Status: ${item.status}
${item.description ? `Description: ${item.description}` : ''}
                `;
                alert(details);
            }
        }

        function viewEmployee(id) {
            const employee = employees.find(e => e.id === id);
            if (employee) {
                const details = `
Employee Details:
Name: ${employee.name}
Position: ${employee.position}
Department: ${employee.department}
Email: ${employee.email}
Phone: ${employee.phone}
Salary: KSh ${employee.salary.toFixed(2)}
Status: ${employee.status}
                `;
                alert(details);
            }
        }

        function viewCustomer(id) {
            const customer = customers.find(c => c.id === id);
            if (customer) {
                const details = `
Customer Details:
Name: ${customer.name}
Email: ${customer.email}
Phone: ${customer.phone}
Company: ${customer.company || 'N/A'}
Total Spent: KSh ${customer.totalSpent.toFixed(2)}
${customer.address ? `Address: ${customer.address}` : ''}
                `;
                alert(details);
            }
        }

        function viewVendor(id) {
            const vendor = vendors.find(v => v.id === id);
            if (vendor) {
                const details = `
Vendor Details:
Name: ${vendor.name}
Email: ${vendor.email}
Phone: ${vendor.phone}
Category: ${vendor.category}
Total Billed: KSh ${vendor.totalBilled.toFixed(2)}
${vendor.address ? `Address: ${vendor.address}` : ''}
                `;
                alert(details);
            }
        }

        function viewCategory(id) {
            const category = categories.find(c => c.id === id);
            if (category) {
                const details = `
Category Details:
Name: ${category.name}
Type: ${category.type}
Description: ${category.description || 'N/A'}
Items Count: ${category.itemCount}
                `;
                alert(details);
            }
        }

        function viewTransaction(id) {
            const transaction = transactions.find(t => t.id === id);
            if (transaction) {
                const details = `
Transaction Details:
Date: ${formatDate(transaction.date)}
Description: ${transaction.description}
Type: ${transaction.type}
Category: ${transaction.category}
Amount: KSh ${Math.abs(transaction.amount).toFixed(2)}
${transaction.notes ? `Notes: ${transaction.notes}` : ''}
                `;
                alert(details);
            }
        }

        // CSV Import functionality
        function importCSV(type, input) {
            const file = input.files[0];
            if (!file) return;
            
            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const csvData = e.target.result;
                    const rows = csvData.split('\n').filter(row => row.trim());
                    const headers = rows[0].split(',').map(h => h.trim().toLowerCase());
                    
                    let importedCount = 0;
                    
                    for (let i = 1; i < rows.length; i++) {
                        const values = rows[i].split(',').map(v => v.trim());
                        if (values.length === headers.length) {
                            const item = {};
                            headers.forEach((header, index) => {
                                item[header] = values[index];
                            });
                            
                            if (type === 'invoices') {
                                // Convert CSV data to invoice format
                                const invoice = {
                                    id: Date.now().toString() + i,
                                    number: item.number || `IMPORT-${i}`,
                                    date: item.date || new Date().toISOString().split('T')[0],
                                    dueDate: item.duedate || new Date().toISOString().split('T')[0],
                                    clientId: 'imported',
                                    clientName: item.client || 'Imported Client',
                                    items: [{
                                        description: item.description || 'Imported Item',
                                        quantity: parseFloat(item.quantity) || 1,
                                        price: parseFloat(item.amount) || parseFloat(item.total) || 0,
                                        total: parseFloat(item.amount) || parseFloat(item.total) || 0
                                    }],
                                    subtotal: parseFloat(item.subtotal) || parseFloat(item.amount) || parseFloat(item.total) || 0,
                                    vat: parseFloat(item.vat) || 0,
                                    total: parseFloat(item.total) || parseFloat(item.amount) || 0,
                                    status: item.status || 'pending',
                                    notes: item.notes || '',
                                    createdAt: new Date().toISOString()
                                };
                                invoices.push(invoice);
                                importedCount++;
                            } else if (type === 'bills') {
                                // Convert CSV data to bill format
                                const bill = {
                                    id: Date.now().toString() + i,
                                    number: item.number || `BILL-IMPORT-${i}`,
                                    date: item.date || new Date().toISOString().split('T')[0],
                                    dueDate: item.duedate || new Date().toISOString().split('T')[0],
                                    vendorId: 'imported',
                                    vendorName: item.vendor || 'Imported Vendor',
                                    items: [{
                                        description: item.description || 'Imported Item',
                                        quantity: parseFloat(item.quantity) || 1,
                                        price: parseFloat(item.amount) || parseFloat(item.total) || 0,
                                        total: parseFloat(item.amount) || parseFloat(item.total) || 0
                                    }],
                                    subtotal: parseFloat(item.subtotal) || parseFloat(item.amount) || parseFloat(item.total) || 0,
                                    vat: parseFloat(item.vat) || 0,
                                    total: parseFloat(item.total) || parseFloat(item.amount) || 0,
                                    status: item.status || 'pending',
                                    notes: item.notes || '',
                                    createdAt: new Date().toISOString()
                                };
                                bills.push(bill);
                                importedCount++;
                            }
                        }
                    }
                    
                    saveToLocalStorage();
                    renderAllData();
                    updateDashboard();
                    updateRecentActivity();
                    showToast(`Successfully imported ${importedCount} ${type}`, 'success');
                    
                } catch (error) {
                    console.error('Error importing CSV:', error);
                    showToast('Error importing CSV file. Please check the format.', 'error');
                }
                
                // Reset file input
                input.value = '';
            };
            reader.readAsText(file);
        }

        // CSV Export functionality
        function exportToCsv(type) {
            let data = [];
            let filename = '';
            let headers = [];
            
            if (type === 'invoices') {
                data = invoices;
                filename = 'invoices.csv';
                headers = ['Number', 'Client', 'Date', 'Due Date', 'Subtotal', 'VAT', 'Total', 'Status', 'Notes'];
            } else if (type === 'bills') {
                data = bills;
                filename = 'bills.csv';
                headers = ['Number', 'Vendor', 'Date', 'Due Date', 'Subtotal', 'VAT', 'Total', 'Status', 'Notes'];
            } else if (type === 'inventory') {
                data = inventory;
                filename = 'inventory.csv';
                headers = ['Name', 'SKU', 'Category', 'Quantity', 'Price', 'Status', 'Description'];
            } else if (type === 'employees') {
                data = employees;
                filename = 'employees.csv';
                headers = ['Name', 'Position', 'Department', 'Email', 'Phone', 'Salary', 'Status'];
            } else if (type === 'customers') {
                data = customers;
                filename = 'customers.csv';
                headers = ['Name', 'Email', 'Phone', 'Company', 'Total Spent', 'Address'];
            } else if (type === 'vendors') {
                data = vendors;
                filename = 'vendors.csv';
                headers = ['Name', 'Email', 'Phone', 'Category', 'Total Billed', 'Address'];
            } else if (type === 'transactions') {
                data = transactions;
                filename = 'transactions.csv';
                headers = ['Date', 'Description', 'Type', 'Category', 'Amount', 'Notes'];
            }
            
            if (data.length === 0) {
                showToast(`No ${type} to export`, 'warning');
                return;
            }
            
            let csvContent = headers.join(',') + '\n';
            
            data.forEach(item => {
                let row = [];
                if (type === 'invoices') {
                    row = [
                        item.number,
                        item.clientName,
                        item.date,
                        item.dueDate,
                        item.subtotal.toFixed(2),
                        item.vat.toFixed(2),
                        item.total.toFixed(2),
                        item.status,
                        `"${(item.notes || '').replace(/"/g, '""')}"`
                    ];
                } else if (type === 'bills') {
                    row = [
                        item.number,
                        item.vendorName,
                        item.date,
                        item.dueDate,
                        item.subtotal.toFixed(2),
                        item.vat.toFixed(2),
                        item.total.toFixed(2),
                        item.status,
                        `"${(item.notes || '').replace(/"/g, '""')}"`
                    ];
                } else if (type === 'inventory') {
                    row = [
                        item.name,
                        item.sku,
                        item.category,
                        item.quantity,
                        item.price.toFixed(2),
                        item.status,
                        `"${(item.description || '').replace(/"/g, '""')}"`
                    ];
                } else if (type === 'employees') {
                    row = [
                        item.name,
                        item.position,
                        item.department,
                        item.email,
                        item.phone,
                        item.salary.toFixed(2),
                        item.status
                    ];
                } else if (type === 'customers') {
                    row = [
                        item.name,
                        item.email,
                        item.phone,
                        item.company || '',
                        item.totalSpent.toFixed(2),
                        `"${(item.address || '').replace(/"/g, '""')}"`
                    ];
                } else if (type === 'vendors') {
                    row = [
                        item.name,
                        item.email,
                        item.phone,
                        item.category,
                        item.totalBilled.toFixed(2),
                        `"${(item.address || '').replace(/"/g, '""')}"`
                    ];
                } else if (type === 'transactions') {
                    row = [
                        item.date,
                        item.description,
                        item.type,
                        item.category,
                        Math.abs(item.amount).toFixed(2),
                        `"${(item.notes || '').replace(/"/g, '""')}"`
                    ];
                }
                csvContent += row.join(',') + '\n';
            });
            
            // Create download link
            const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
            const link = document.createElement('a');
            const url = URL.createObjectURL(blob);
            
            link.setAttribute('href', url);
            link.setAttribute('download', filename);
            link.style.visibility = 'hidden';
            
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
            
            showToast(`Exported ${data.length} ${type} successfully`, 'success');
        }

        // Generate sample data
        function generateSampleData() {
            // Generate sample customers
            if (customers.length === 0) {
                customers = [
                    { id: '1', name: 'John Doe Enterprises', email: 'john@doe.com', phone: '+254712345678', company: 'John Doe Enterprises', totalSpent: 70800 },
                    { id: '2', name: 'Jane Smith Ltd', email: 'jane@smith.com', phone: '+254723456789', company: 'Jane Smith Ltd', totalSpent: 0 },
                    { id: '3', name: 'ABC Corporation', email: 'contact@abc.com', phone: '+254734567890', company: 'ABC Corporation', totalSpent: 0 }
                ];
            }
            
            // Generate sample vendors
            if (vendors.length === 0) {
                vendors = [
                    { id: '1', name: 'Office Supplies Kenya', email: 'info@officesupplies.co.ke', phone: '+254745678901', category: 'Office Supplies', totalBilled: 54870 },
                    { id: '2', name: 'Tech Solutions Ltd', email: 'sales@techsolutions.co.ke', phone: '+254756789012', category: 'Technology', totalBilled: 177000 },
                    { id: '3', name: 'Utilities Company', email: 'billing@utilities.co.ke', phone: '+254767890123', category: 'Utilities', totalBilled: 0 }
                ];
            }
            
            // Generate sample categories
            if (categories.length === 0) {
                categories = [
                    { id: '1', name: 'Office Supplies', type: 'expense', description: 'Office stationery and supplies', itemCount: 2 },
                    { id: '2', name: 'Technology', type: 'expense', description: 'Computers and software', itemCount: 1 },
                    { id: '3', name: 'Services', type: 'income', description: 'Consulting and professional services', itemCount: 2 },
                    { id: '4', name: 'Utilities', type: 'expense', description: 'Electricity, water, internet', itemCount: 0 }
                ];
            }
            
            // Generate sample inventory
            if (inventory.length === 0) {
                inventory = [
                    { id: '1', name: 'Office Chair', sku: 'CHAIR-001', category: '1', quantity: 15, price: 4500, status: 'in-stock', description: 'Ergonomic office chair' },
                    { id: '2', name: 'Desk', sku: 'DESK-001', category: '1', quantity: 8, price: 8000, status: 'low-stock', description: 'Executive office desk' },
                    { id: '3', name: 'Laptop', sku: 'LAPTOP-001', category: '2', quantity: 5, price: 75000, status: 'low-stock', description: 'Business laptop' }
                ];
            }
            
            // Generate sample employees
            if (employees.length === 0) {
                employees = [
                    { id: '1', name: 'David Kimani', position: 'Manager', department: 'Operations', email: 'david@company.com', phone: '+254778901234', salary: 80000, status: 'active' },
                    { id: '2', name: 'Sarah Mwangi', position: 'Accountant', department: 'Finance', email: 'sarah@company.com', phone: '+254789012345', salary: 60000, status: 'active' },
                    { id: '3', name: 'Peter Ochieng', position: 'Sales Executive', department: 'Sales', email: 'peter@company.com', phone: '+254790123456', salary: 45000, status: 'active' }
                ];
            }
            
            // Generate sample invoices if none exist
            if (invoices.length === 0) {
                const sampleInvoices = [
                    {
                        id: '1',
                        number: 'INV-001',
                        date: '2023-10-01',
                        dueDate: '2023-10-15',
                        clientId: '1',
                        clientName: 'John Doe Enterprises',
                        items: [
                            { description: 'Web Development Services', quantity: 10, price: 5000, total: 50000 },
                            { description: 'Consulting Hours', quantity: 5, price: 2000, total: 10000 }
                        ],
                        subtotal: 60000,
                        vat: 10800,
                        total: 70800,
                        status: 'paid',
                        notes: 'Thank you for your business!',
                        createdAt: '2023-10-01T10:00:00Z'
                    },
                    {
                        id: '2',
                        number: 'INV-002',
                        date: '2023-10-05',
                        dueDate: '2023-10-20',
                        clientId: '2',
                        clientName: 'Jane Smith Ltd',
                        items: [
                            { description: 'Mobile App Development', quantity: 1, price: 150000, total: 150000 }
                        ],
                        subtotal: 150000,
                        vat: 27000,
                        total: 177000,
                        status: 'pending',
                        notes: '',
                        createdAt: '2023-10-05T14:30:00Z'
                    }
                ];
                invoices.push(...sampleInvoices);
            }
            
            // Generate sample bills if none exist
            if (bills.length === 0) {
                const sampleBills = [
                    {
                        id: '1',
                        number: 'BL-001',
                        date: '2023-10-02',
                        dueDate: '2023-10-16',
                        vendorId: '1',
                        vendorName: 'Office Supplies Kenya',
                        items: [
                            { description: 'Office Chairs', quantity: 5, price: 4500, total: 22500 },
                            { description: 'Desks', quantity: 3, price: 8000, total: 24000 }
                        ],
                        subtotal: 46500,
                        vat: 8370,
                        total: 54870,
                        status: 'paid',
                        notes: 'Delivery expected next week',
                        createdAt: '2023-10-02T09:15:00Z'
                    },
                    {
                        id: '2',
                        number: 'BL-002',
                        date: '2023-10-10',
                        dueDate: '2023-10-25',
                        vendorId: '2',
                        vendorName: 'Tech Solutions Ltd',
                        items: [
                            { description: 'Laptops', quantity: 2, price: 75000, total: 150000 }
                        ],
                        subtotal: 150000,
                        vat: 27000,
                        total: 177000,
                        status: 'pending',
                        notes: '',
                        createdAt: '2023-10-10T11:45:00Z'
                    }
                ];
                bills.push(...sampleBills);
            }
            
            // Generate sample transactions
            if (transactions.length === 0) {
                transactions = [
                    { id: '1', date: '2023-10-01', description: 'Invoice INV-001 Payment', type: 'income', category: '3', amount: 70800, notes: 'Payment received for invoice INV-001' },
                    { id: '2', date: '2023-10-02', description: 'Office Supplies Purchase', type: 'expense', category: '1', amount: -54870, notes: 'Office furniture purchase' },
                    { id: '3', date: '2023-10-05', description: 'Invoice INV-002 Created', type: 'income', category: '3', amount: 177000, notes: 'Invoice issued to Jane Smith Ltd' },
                    { id: '4', date: '2023-10-10', description: 'Tech Equipment Purchase', type: 'expense', category: '2', amount: -177000, notes: 'Laptops for new employees' }
                ];
            }
            
            // Generate sample tax rules
            if (taxRules.length === 0) {
                taxRules = [
                    { id: '1', name: 'VAT Standard', rate: 16, type: 'vat', applicable: 'all', createdAt: new Date().toISOString() },
                    { id: '2', name: 'Withholding Tax', rate: 5, type: 'income', applicable: 'services', createdAt: new Date().toISOString() }
                ];
            }
            
            saveToLocalStorage();
            renderAllData();
            updateDashboard();
            updateRecentActivity();
            showToast('Sample data generated successfully!', 'success');
        }

        // Report functions
        function generateSalesReport() {
            const startDate = document.getElementById('reportStartDate').value;
            const endDate = document.getElementById('reportEndDate').value;
            
            const filteredInvoices = invoices.filter(inv => {
                const invoiceDate = new Date(inv.date);
                const start = new Date(startDate);
                const end = new Date(endDate);
                return invoiceDate >= start && invoiceDate <= end;
            });
            
            const totalSales = filteredInvoices.reduce((sum, inv) => sum + inv.total, 0);
            const paidInvoices = filteredInvoices.filter(inv => inv.status === 'paid');
            const pendingInvoices = filteredInvoices.filter(inv => inv.status === 'pending');
            
            const reportContent = `
                <h3>Sales Report (${formatDate(startDate)} to ${formatDate(endDate)})</h3>
                <div class="stats-container">
                    <div class="stat-card">
                        <div class="stat-label">Total Sales</div>
                        <div class="stat-value">KSh ${totalSales.toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Paid Invoices</div>
                        <div class="stat-value">${paidInvoices.length}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Pending Invoices</div>
                        <div class="stat-value">${pendingInvoices.length}</div>
                    </div>
                </div>
                <table>
                    <thead>
                        <tr>
                            <th>Invoice #</th>
                            <th>Client</th>
                            <th>Date</th>
                            <th>Amount</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        ${filteredInvoices.map(inv => `
                            <tr>
                                <td>${inv.number}</td>
                                <td>${inv.clientName}</td>
                                <td>${formatDate(inv.date)}</td>
                                <td>KSh ${inv.total.toFixed(2)}</td>
                                <td><span class="status-badge ${inv.status}">${inv.status}</span></td>
                            </tr>
                        `).join('')}
                    </tbody>
                </table>
            `;
            
            document.getElementById('reportContent').innerHTML = reportContent;
            showToast('Sales report generated successfully!', 'success');
        }

        function generateExpenseReport() {
            const startDate = document.getElementById('reportStartDate').value;
            const endDate = document.getElementById('reportEndDate').value;
            
            const filteredBills = bills.filter(bill => {
                const billDate = new Date(bill.date);
                const start = new Date(startDate);
                const end = new Date(endDate);
                return billDate >= start && billDate <= end;
            });
            
            const totalExpenses = filteredBills.reduce((sum, bill) => sum + bill.total, 0);
            const paidBills = filteredBills.filter(bill => bill.status === 'paid');
            const pendingBills = filteredBills.filter(bill => bill.status === 'pending');
            
            const reportContent = `
                <h3>Expense Report (${formatDate(startDate)} to ${formatDate(endDate)})</h3>
                <div class="stats-container">
                    <div class="stat-card">
                        <div class="stat-label">Total Expenses</div>
                        <div class="stat-value">KSh ${totalExpenses.toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Paid Bills</div>
                        <div class="stat-value">${paidBills.length}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Pending Bills</div>
                        <div class="stat-value">${pendingBills.length}</div>
                    </div>
                </div>
                <table>
                    <thead>
                        <tr>
                            <th>Bill #</th>
                            <th>Vendor</th>
                            <th>Date</th>
                            <th>Amount</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        ${filteredBills.map(bill => `
                            <tr>
                                <td>${bill.number}</td>
                                <td>${bill.vendorName}</td>
                                <td>${formatDate(bill.date)}</td>
                                <td>KSh ${bill.total.toFixed(2)}</td>
                                <td><span class="status-badge ${bill.status}">${bill.status}</span></td>
                            </tr>
                        `).join('')}
                    </tbody>
                </table>
            `;
            
            document.getElementById('reportContent').innerHTML = reportContent;
            showToast('Expense report generated successfully!', 'success');
        }

        function generateProfitLossReport() {
            const startDate = document.getElementById('reportStartDate').value;
            const endDate = document.getElementById('reportEndDate').value;
            
            const income = transactions
                .filter(t => t.type === 'income' && new Date(t.date) >= new Date(startDate) && new Date(t.date) <= new Date(endDate))
                .reduce((sum, t) => sum + t.amount, 0);
                
            const expenses = transactions
                .filter(t => t.type === 'expense' && new Date(t.date) >= new Date(startDate) && new Date(t.date) <= new Date(endDate))
                .reduce((sum, t) => sum + t.amount, 0);
                
            const profit = income + expenses; // Expenses are negative, so we add them
            
            const reportContent = `
                <h3>Profit & Loss Report (${formatDate(startDate)} to ${formatDate(endDate)})</h3>
                <div class="stats-container">
                    <div class="stat-card">
                        <div class="stat-label">Total Income</div>
                        <div class="stat-value" style="color: var(--success);">KSh ${income.toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Total Expenses</div>
                        <div class="stat-value" style="color: var(--danger);">KSh ${Math.abs(expenses).toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Net Profit</div>
                        <div class="stat-value" style="color: ${profit >= 0 ? 'var(--success)' : 'var(--danger)'};">KSh ${profit.toFixed(2)}</div>
                    </div>
                </div>
            `;
            
            document.getElementById('reportContent').innerHTML = reportContent;
            showToast('Profit & Loss report generated successfully!', 'success');
        }

        function generateTaxReport() {
            const taxYear = document.getElementById('taxYear').value;
            
            const yearlyTransactions = transactions.filter(t => {
                const transactionYear = new Date(t.date).getFullYear().toString();
                return transactionYear === taxYear;
            });
            
            const taxableIncome = yearlyTransactions
                .filter(t => t.type === 'income')
                .reduce((sum, t) => sum + t.amount, 0);
                
            const deductibleExpenses = yearlyTransactions
                .filter(t => t.type === 'expense')
                .reduce((sum, t) => sum + Math.abs(t.amount), 0);
                
            const netIncome = taxableIncome - deductibleExpenses;
            const taxLiability = netIncome * 0.3; // Assuming 30% tax rate
            
            const reportContent = `
                <h3>Tax Report for ${taxYear}</h3>
                <div class="stats-container">
                    <div class="stat-card">
                        <div class="stat-label">Taxable Income</div>
                        <div class="stat-value">KSh ${taxableIncome.toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Deductible Expenses</div>
                        <div class="stat-value">KSh ${deductibleExpenses.toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Net Income</div>
                        <div class="stat-value">KSh ${netIncome.toFixed(2)}</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-label">Estimated Tax</div>
                        <div class="stat-value" style="color: var(--warning);">KSh ${taxLiability.toFixed(2)}</div>
                    </div>
                </div>
            `;
            
            document.getElementById('reportContent').innerHTML = reportContent;
            showToast('Tax report generated successfully!', 'success');
        }

        function generateReport() {
            const reportType = document.getElementById('reportType').value;
            
            if (reportType === 'sales') {
                generateSalesReport();
            } else if (reportType === 'expenses') {
                generateExpenseReport();
            } else if (reportType === 'profit') {
                generateProfitLossReport();
            } else if (reportType === 'tax') {
                generateTaxReport();
            }
        }

        // Tax calculation
        function calculateTaxes() {
            const taxYear = document.getElementById('taxYear').value;
            const taxType = document.getElementById('taxType').value;
            
            let taxAmount = 0;
            let calculationDetails = '';
            
            if (taxType === 'vat') {
                const vatRate = taxRules.find(t => t.type === 'vat')?.rate || 16;
                const vatTransactions = transactions.filter(t => {
                    const transactionYear = new Date(t.date).getFullYear().toString();
                    return transactionYear === taxYear;
                });
                
                const vatOnSales = vatTransactions
                    .filter(t => t.type === 'income')
                    .reduce((sum, t) => sum + (t.amount * vatRate / (100 + vatRate)), 0);
                    
                const vatOnPurchases = vatTransactions
                    .filter(t => t.type === 'expense')
                    .reduce((sum, t) => sum + (Math.abs(t.amount) * vatRate / (100 + vatRate)), 0);
                    
                taxAmount = vatOnSales - vatOnPurchases;
                
                calculationDetails = `
                    <h4>VAT Calculation for ${taxYear}</h4>
                    <p>VAT Rate: ${vatRate}%</p>
                    <p>VAT on Sales: KSh ${vatOnSales.toFixed(2)}</p>
                    <p>VAT on Purchases: KSh ${vatOnPurchases.toFixed(2)}</p>
                    <p><strong>Net VAT Payable: KSh ${taxAmount.toFixed(2)}</strong></p>
                `;
            } else if (taxType === 'income') {
                const incomeTaxRate = 0.3; // 30% for simplicity
                const yearlyTransactions = transactions.filter(t => {
                    const transactionYear = new Date(t.date).getFullYear().toString();
                    return transactionYear === taxYear;
                });
                
                const taxableIncome = yearlyTransactions
                    .filter(t => t.type === 'income')
                    .reduce((sum, t) => sum + t.amount, 0);
                    
                const deductibleExpenses = yearlyTransactions
                    .filter(t => t.type === 'expense')
                    .reduce((sum, t) => sum + Math.abs(t.amount), 0);
                    
                const netIncome = taxableIncome - deductibleExpenses;
                taxAmount = netIncome * incomeTaxRate;
                
                calculationDetails = `
                    <h4>Income Tax Calculation for ${taxYear}</h4>
                    <p>Taxable Income: KSh ${taxableIncome.toFixed(2)}</p>
                    <p>Deductible Expenses: KSh ${deductibleExpenses.toFixed(2)}</p>
                    <p>Net Income: KSh ${netIncome.toFixed(2)}</p>
                    <p>Tax Rate: 30%</p>
                    <p><strong>Income Tax Payable: KSh ${taxAmount.toFixed(2)}</strong></p>
                `;
            }
            
            document.getElementById('taxCalculationResults').innerHTML = calculationDetails;
            showToast('Tax calculation completed!', 'success');
        }

        // Settings functions
        function saveSettings() {
            settings = {
                businessName: document.getElementById('businessName').value,
                businessAddress: document.getElementById('businessAddress').value,
                businessPhone: document.getElementById('businessPhone').value,
                businessEmail: document.getElementById('businessEmail').value,
                currency: document.getElementById('currency').value,
                dateFormat: document.getElementById('dateFormat').value,
                taxId: document.getElementById('taxId').value
            };
            
            localStorage.setItem('recordBookSettings', JSON.stringify(settings));
            showToast('Settings saved successfully!', 'success');
        }

        function resetSettings() {
            document.getElementById('businessName').value = '';
            document.getElementById('businessAddress').value = '';
            document.getElementById('businessPhone').value = '';
            document.getElementById('businessEmail').value = '';
            document.getElementById('currency').value = 'KSh';
            document.getElementById('dateFormat').value = 'dd/mm/yyyy';
            document.getElementById('taxId').value = '';
            
            showToast('Settings reset to default!', 'success');
        }

        function clearAllData() {
            if (confirm('Are you sure you want to clear ALL data? This action cannot be undone.')) {
                invoices = [];
                bills = [];
                inventory = [];
                employees = [];
                customers = [];
                vendors = [];
                categories = [];
                transactions = [];
                taxRules = [];
                
                saveToLocalStorage();
                renderAllData();
                updateDashboard();
                updateRecentActivity();
                showToast('All data cleared!', 'success');
            }
        }

        // Add status update functionality
        function updateInvoiceStatus(invoiceId, status) {
            const invoice = invoices.find(inv => inv.id === invoiceId);
            if (invoice) {
                invoice.status = status;
                saveToLocalStorage();
                renderInvoices();
                updateDashboard();
                showToast(`Invoice status updated to ${status}`, 'success');
            }
        }

        function updateBillStatus(billId, status) {
            const bill = bills.find(b => b.id === billId);
            if (bill) {
                bill.status = status;
                saveToLocalStorage();
                renderBills();
                updateDashboard();
                showToast(`Bill status updated to ${status}`, 'success');
            }
        }
    </script>
</body>
</html>
