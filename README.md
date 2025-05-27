<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LOTERÍA PREMIO - Administración</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --dark: #2d3436;
            --light: #f5f6fa;
            --success: #00b894;
            --danger: #d63031;
            --warning: #fdcb6e;
            --info: #0984e3;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background-color: #f1f3f6;
            color: var(--dark);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 20px 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 24px;
            font-weight: 700;
        }
        
        .admin-nav {
            display: flex;
            align-items: center;
        }
        
        .admin-nav ul {
            display: flex;
            list-style: none;
        }
        
        .admin-nav ul li {
            margin-left: 20px;
        }
        
        .admin-nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .admin-nav ul li a:hover {
            opacity: 0.8;
        }
        
        .admin-nav .user-info {
            display: flex;
            align-items: center;
            margin-left: 20px;
        }
        
        .admin-nav .user-info img {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            margin-right: 10px;
            object-fit: cover;
        }
        
        .btn {
            padding: 8px 16px;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .btn-primary {
            background-color: white;
            color: var(--primary);
        }
        
        .btn-outline {
            background-color: transparent;
            color: white;
            border: 1px solid white;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        .admin-content {
            display: flex;
            margin-top: 30px;
        }
        
        .sidebar {
            width: 250px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            padding: 20px;
            margin-right: 20px;
        }
        
        .sidebar-menu {
            list-style: none;
        }
        
        .sidebar-menu li {
            margin-bottom: 10px;
        }
        
        .sidebar-menu a {
            display: block;
            padding: 10px;
            color: var(--dark);
            text-decoration: none;
            border-radius: 5px;
            transition: all 0.3s ease;
        }
        
        .sidebar-menu a:hover, .sidebar-menu a.active {
            background-color: var(--secondary);
            color: white;
        }
        
        .sidebar-menu i {
            margin-right: 10px;
            width: 20px;
            text-align: center;
        }
        
        .main-content {
            flex: 1;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            padding: 30px;
        }
        
        .section-title {
            font-size: 24px;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            text-align: center;
        }
        
        .stat-card i {
            font-size: 30px;
            margin-bottom: 10px;
        }
        
        .stat-card .value {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .stat-card .label {
            color: #666;
            font-size: 14px;
        }
        
        .stat-card.primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
        }
        
        .stat-card.primary .label {
            color: rgba(255, 255, 255, 0.8);
        }
        
        .stat-card.success {
            background-color: var(--success);
            color: white;
        }
        
        .stat-card.success .label {
            color: rgba(255, 255, 255, 0.8);
        }
        
        .stat-card.warning {
            background-color: var(--warning);
            color: var(--dark);
        }
        
        .stat-card.danger {
            background-color: var(--danger);
            color: white;
        }
        
        .stat-card.danger .label {
            color: rgba(255, 255, 255, 0.8);
        }
        
        .table-responsive {
            overflow-x: auto;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }
        
        th {
            background-color: #f8f9fa;
            font-weight: 600;
            color: var(--dark);
        }
        
        tr:hover {
            background-color: #f8f9fa;
        }
        
        .status {
            padding: 5px 10px;
            border-radius: 4px;
            font-weight: 600;
            font-size: 12px;
            text-align: center;
        }
        
        .status.pending {
            background-color: var(--warning);
            color: var(--dark);
        }
        
        .status.confirmed {
            background-color: var(--success);
            color: white;
        }
        
        .status.rejected {
            background-color: var(--danger);
            color: white;
        }
        
        .action-btn {
            padding: 5px 10px;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-size: 12px;
            transition: all 0.3s ease;
        }
        
        .action-btn.confirm {
            background-color: var(--success);
            color: white;
        }
        
        .action-btn.reject {
            background-color: var(--danger);
            color: white;
            margin-left: 5px;
        }
        
        .action-btn:hover {
            opacity: 0.8;
        }
        
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
        }
        
        .modal-content {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            max-width: 600px;
            width: 90%;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 24px;
            cursor: pointer;
            color: var(--dark);
        }
        
        .modal-title {
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .ticket-details div {
            margin-bottom: 15px;
        }
        
        .ticket-details span {
            font-weight: 600;
        }
        
        .receipt-img {
            max-width: 100%;
            border-radius: 5px;
            margin-top: 15px;
        }
        
        .user-info-modal {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }
        
        .user-info-modal h4 {
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .modal-actions {
            display: flex;
            justify-content: flex-end;
            margin-top: 20px;
        }
        
        .modal-actions button {
            margin-left: 10px;
        }
        
        .search-filter {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }
        
        .search-box {
            position: relative;
            width: 300px;
        }
        
        .search-box input {
            width: 100%;
            padding: 10px 15px 10px 40px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 14px;
        }
        
        .search-box i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: #666;
        }
        
        .filter-select {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 14px;
        }
        
        .pagination {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        
        .pagination button {
            padding: 8px 12px;
            margin: 0 5px;
            border: 1px solid #ddd;
            background-color: white;
            cursor: pointer;
            border-radius: 4px;
        }
        
        .pagination button.active {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary);
        }
        
        .pagination button:hover:not(.active) {
            background-color: #f8f9fa;
        }
        
        @media (max-width: 992px) {
            .admin-content {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                margin-right: 0;
                margin-bottom: 20px;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .header-content {
                flex-direction: column;
            }
            
            .admin-nav {
                margin-top: 15px;
                width: 100%;
                justify-content: space-between;
            }
            
            .search-box {
                width: 100%;
                margin-bottom: 15px;
            }
            
            .search-filter {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">LOTERÍA PREMIO - ADMIN</div>
            <div class="admin-nav">
                <ul>
                    <li><a href="#"><i class="fas fa-home"></i> Inicio</a></li>
                    <li><a href="#"><i class="fas fa-cog"></i> Configuración</a></li>
                </ul>
                <div class="user-info">
                    <img src="https://via.placeholder.com/150" alt="Admin" id="adminPhoto">
                    <span id="adminName">Administrador</span>
                </div>
            </div>
        </div>
    </header>

    <div class="container admin-content">
        <aside class="sidebar">
            <ul class="sidebar-menu">
                <li><a href="#" class="active"><i class="fas fa-tachometer-alt"></i> Dashboard</a></li>
                <li><a href="#"><i class="fas fa-ticket-alt"></i> Tickets</a></li>
                <li><a href="#"><i class="fas fa-users"></i> Usuarios</a></li>
                <li><a href="#"><i class="fas fa-chart-bar"></i> Reportes</a></li>
                <li><a href="#"><i class="fas fa-gift"></i> Premios</a></li>
                <li><a href="#"><i class="fas fa-money-bill-wave"></i> Pagos</a></li>
                <li><a href="#"><i class="fas fa-bell"></i> Notificaciones</a></li>
                <li><a href="#" id="logoutBtn"><i class="fas fa-sign-out-alt"></i> Cerrar Sesión</a></li>
            </ul>
        </aside>

        <main class="main-content">
            <h2 class="section-title">Panel de Administración</h2>
            
            <div class="stats-grid">
                <div class="stat-card primary">
                    <i class="fas fa-ticket-alt"></i>
                    <div class="value" id="totalTickets">0</div>
                    <div class="label">Tickets Totales</div>
                </div>
                <div class="stat-card success">
                    <i class="fas fa-check-circle"></i>
                    <div class="value" id="confirmedTickets">0</div>
                    <div class="label">Confirmados</div>
                </div>
                <div class="stat-card warning">
                    <i class="fas fa-clock"></i>
                    <div class="value" id="pendingTickets">0</div>
                    <div class="label">Pendientes</div>
                </div>
                <div class="stat-card danger">
                    <i class="fas fa-times-circle"></i>
                    <div class="value" id="rejectedTickets">0</div>
                    <div class="label">Rechazados</div>
                </div>
            </div>
            
            <div class="search-filter">
                <div class="search-box">
                    <i class="fas fa-search"></i>
                    <input type="text" id="searchInput" placeholder="Buscar tickets...">
                </div>
                <select class="filter-select" id="statusFilter">
                    <option value="all">Todos los estados</option>
                    <option value="pending">Pendientes</option>
                    <option value="confirmed">Confirmados</option>
                    <option value="rejected">Rechazados</option>
                </select>
            </div>
            
            <div class="table-responsive">
                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Usuario</th>
                            <th>Números</th>
                            <th>Monto</th>
                            <th>Fecha</th>
                            <th>Estado</th>
                            <th>Acciones</th>
                        </tr>
                    </thead>
                    <tbody id="ticketsTable">
                        <!-- Tickets will be loaded by JavaScript -->
                    </tbody>
                </table>
            </div>
            
            <div class="pagination">
                <button id="prevPage"><i class="fas fa-chevron-left"></i></button>
                <button class="active">1</button>
                <button>2</button>
                <button>3</button>
                <button id="nextPage"><i class="fas fa-chevron-right"></i></button>
            </div>
        </main>
    </div>

    <!-- Ticket Detail Modal -->
    <div class="modal" id="ticketModal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">Detalle del Ticket <span id="modalTicketId"></span></h3>
            
            <div class="ticket-details">
                <div>
                    <span>Números jugados:</span> <span id="modalNumbers"></span>
                </div>
                <div>
                    <span>Apuesta por número:</span> $<span id="modalBetPerNumber"></span>
                </div>
                <div>
                    <span>Apuesta total:</span> $<span id="modalTotalBet"></span>
                </div>
                <div>
                    <span>Fecha:</span> <span id="modalDate"></span>
                </div>
                <div>
                    <span>Estado:</span> <span class="status" id="modalStatus"></span>
                </div>
                <div>
                    <span>Comprobante:</span>
                    <img id="modalReceipt" class="receipt-img" alt="Comprobante de pago">
                </div>
            </div>
            
            <div class="user-info-modal">
                <h4>Información del Usuario</h4>
                <div>
                    <span>Nombre:</span> <span id="modalUserName"></span>
                </div>
                <div>
                    <span>Email:</span> <span id="modalUserEmail"></span>
                </div>
                <div>
                    <span>Teléfono:</span> <span id="modalUserPhone"></span>
                </div>
            </div>
            
            <div class="modal-actions" id="modalActions">
                <button class="btn action-btn confirm" id="confirmTicket">Confirmar</button>
                <button class="btn action-btn reject" id="rejectTicket">Rechazar</button>
            </div>
        </div>
    </div>

    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-storage.js"></script>
    
    <script>
        // Firebase configuration
        const firebaseConfig = {
            apiKey: "AIzaSyBi19o_saTQEXMUJ3cSGyhv5oq21X1O4Sg",
            authDomain: "rifa-8e8da.firebaseapp.com",
            databaseURL: "https://rifa-8e8da-default-rtdb.firebaseio.com",
            projectId: "rifa-8e8da",
            storageBucket: "rifa-8e8da.appspot.com",
            messagingSenderId: "1037499089060",
            appId: "1:1037499089060:web:14826080ba499ca863a631"
        };

        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth();
        const database = firebase.database();
        const storage = firebase.storage();

        // DOM Elements
        const logoutBtn = document.getElementById('logoutBtn');
        const adminPhoto = document.getElementById('adminPhoto');
        const adminName = document.getElementById('adminName');
        const totalTickets = document.getElementById('totalTickets');
        const confirmedTickets = document.getElementById('confirmedTickets');
        const pendingTickets = document.getElementById('pendingTickets');
        const rejectedTickets = document.getElementById('rejectedTickets');
        const searchInput = document.getElementById('searchInput');
        const statusFilter = document.getElementById('statusFilter');
        const ticketsTable = document.getElementById('ticketsTable');
        const prevPage = document.getElementById('prevPage');
        const nextPage = document.getElementById('nextPage');
        const ticketModal = document.getElementById('ticketModal');
        const closeModalButtons = document.querySelectorAll('.close-modal');
        const modalTicketId = document.getElementById('modalTicketId');
        const modalNumbers = document.getElementById('modalNumbers');
        const modalBetPerNumber = document.getElementById('modalBetPerNumber');
        const modalTotalBet = document.getElementById('modalTotalBet');
        const modalDate = document.getElementById('modalDate');
        const modalStatus = document.getElementById('modalStatus');
        const modalReceipt = document.getElementById('modalReceipt');
        const modalUserName = document.getElementById('modalUserName');
        const modalUserEmail = document.getElementById('modalUserEmail');
        const modalUserPhone = document.getElementById('modalUserPhone');
        const modalActions = document.getElementById('modalActions');
        const confirmTicket = document.getElementById('confirmTicket');
        const rejectTicket = document.getElementById('rejectTicket');

        // App state
        let currentUser = null;
        let tickets = [];
        let filteredTickets = [];
        let currentTicket = null;
        let currentPage = 1;
        const ticketsPerPage = 10;

        // Initialize app
        function init() {
            setupAuth();
            setupEventListeners();
            loadTickets();
        }

        // Setup authentication
        function setupAuth() {
            auth.onAuthStateChanged((user) => {
                if (user) {
                    currentUser = user;
                    updateAdminInfo(user);
                } else {
                    window.location.href = 'index.html';
                }
            });
            
            logoutBtn.addEventListener('click', () => {
                auth.signOut();
            });
        }

        // Update admin info
        function updateAdminInfo(user) {
            adminName.textContent = user.email;
            
            // Load additional admin data from database
            database.ref('admins/' + user.uid).once('value')
                .then((snapshot) => {
                    const adminData = snapshot.val();
                    if (adminData) {
                        if (adminData.name) adminName.textContent = adminData.name;
                        if (adminData.photoUrl) adminPhoto.src = adminData.photoUrl;
                    }
                });
        }

        // Setup event listeners
        function setupEventListeners() {
            // Search and filter
            searchInput.addEventListener('input', filterTickets);
            statusFilter.addEventListener('change', filterTickets);
            
            // Pagination
            prevPage.addEventListener('click', () => {
                if (currentPage > 1) {
                    currentPage--;
                    renderTickets();
                }
            });
            
            nextPage.addEventListener('click', () => {
                if (currentPage < Math.ceil(filteredTickets.length / ticketsPerPage)) {
                    currentPage++;
                    renderTickets();
                }
            });
            
            // Modal
            closeModalButtons.forEach(button => {
                button.addEventListener('click', () => {
                    ticketModal.style.display = 'none';
                });
            });
            
            window.addEventListener('click', (e) => {
                if (e.target === ticketModal) {
                    ticketModal.style.display = 'none';
                }
            });
            
            // Ticket actions
            confirmTicket.addEventListener('click', () => {
                if (currentTicket) {
                    updateTicketStatus(currentTicket.id, 'confirmed');
                }
            });
            
            rejectTicket.addEventListener('click', () => {
                if (currentTicket) {
                    updateTicketStatus(currentTicket.id, 'rejected');
                }
            });
        }

        // Load tickets from database
        function loadTickets() {
            database.ref('tickets').on('value', (snapshot) => {
                tickets = [];
                snapshot.forEach((childSnapshot) => {
                    const ticket = childSnapshot.val();
                    ticket.id = childSnapshot.key;
                    tickets.push(ticket);
                });
                
                // Sort by date (newest first)
                tickets.sort((a, b) => b.date - a.date);
                
                filterTickets();
                updateStats();
            });
        }

        // Filter tickets based on search and status
        function filterTickets() {
            const searchTerm = searchInput.value.toLowerCase();
            const status = statusFilter.value;
            
            filteredTickets = tickets.filter(ticket => {
                const matchesSearch = ticket.id.toLowerCase().includes(searchTerm) || 
                                     (ticket.userId && ticket.userId.toLowerCase().includes(searchTerm)) ||
                                     ticket.numbers.join(', ').toLowerCase().includes(searchTerm);
                
                const matchesStatus = status === 'all' || ticket.status === status;
                
                return matchesSearch && matchesStatus;
            });
            
            currentPage = 1;
            renderTickets();
        }

        // Render tickets to the table
        function renderTickets() {
            ticketsTable.innerHTML = '';
            
            const startIndex = (currentPage - 1) * ticketsPerPage;
            const endIndex = Math.min(startIndex + ticketsPerPage, filteredTickets.length);
            
            for (let i = startIndex; i < endIndex; i++) {
                const ticket = filteredTickets[i];
                const row = document.createElement('tr');
                
                // Format date
                const date = new Date(ticket.date);
                const dateStr = date.toLocaleDateString() + ' ' + date.toLocaleTimeString();
                
                // Get status class
                let statusClass = '';
                if (ticket.status === 'pending') statusClass = 'pending';
                if (ticket.status === 'confirmed') statusClass = 'confirmed';
                if (ticket.status === 'rejected') statusClass = 'rejected';
                
                row.innerHTML = `
                    <td>${ticket.id}</td>
                    <td>${ticket.userId || 'N/A'}</td>
                    <td>${ticket.numbers.join(', ')}</td>
                    <td>$${ticket.totalBet}</td>
                    <td>${dateStr}</td>
                    <td><span class="status ${statusClass}">${ticket.status.toUpperCase()}</span></td>
                    <td>
                        <button class="action-btn view-btn" data-id="${ticket.id}">Ver</button>
                    </td>
                `;
                
                ticketsTable.appendChild(row);
            }
            
            // Add event listeners to view buttons
            document.querySelectorAll('.view-btn').forEach(button => {
                button.addEventListener('click', (e) => {
                    const ticketId = e.target.getAttribute('data-id');
                    showTicketDetails(ticketId);
                });
            });
            
            // Update pagination buttons
            updatePagination();
        }

        // Update pagination buttons
        function updatePagination() {
            const totalPages = Math.ceil(filteredTickets.length / ticketsPerPage);
            const paginationContainer = document.querySelector('.pagination');
            
            // Clear existing buttons (except prev/next)
            paginationContainer.innerHTML = `
                <button id="prevPage"><i class="fas fa-chevron-left"></i></button>
                ${Array.from({length: totalPages}, (_, i) => 
                    `<button class="${i + 1 === currentPage ? 'active' : ''}">${i + 1}</button>`
                ).join('')}
                <button id="nextPage"><i class="fas fa-chevron-right"></i></button>
            `;
            
            // Re-attach event listeners
            document.getElementById('prevPage').addEventListener('click', () => {
                if (currentPage > 1) {
                    currentPage--;
                    renderTickets();
                }
            });
            
            document.getElementById('nextPage').addEventListener('click', () => {
                if (currentPage < totalPages) {
                    currentPage++;
                    renderTickets();
                }
            });
            
            // Add event listeners to page buttons
            document.querySelectorAll('.pagination button:not(#prevPage):not(#nextPage)').forEach((button, index) => {
                button.addEventListener('click', () => {
                    currentPage = index + 1;
                    renderTickets();
                });
            });
        }

        // Show ticket details in modal
        function showTicketDetails(ticketId) {
            const ticket = tickets.find(t => t.id === ticketId);
            if (!ticket) return;
            
            currentTicket = ticket;
            
            // Format date
            const date = new Date(ticket.date);
            const dateStr = date.toLocaleDateString() + ' ' + date.toLocaleTimeString();
            
            // Update modal content
            modalTicketId.textContent = ticket.id;
            modalNumbers.textContent = ticket.numbers.join(', ');
            modalBetPerNumber.textContent = ticket.betPerNumber;
            modalTotalBet.textContent = ticket.totalBet;
            modalDate.textContent = dateStr;
            
            // Set status
            modalStatus.textContent = ticket.status.toUpperCase();
            modalStatus.className = 'status';
            if (ticket.status === 'pending') modalStatus.classList.add('pending');
            if (ticket.status === 'confirmed') modalStatus.classList.add('confirmed');
            if (ticket.status === 'rejected') modalStatus.classList.add('rejected');
            
            // Load receipt image
            modalReceipt.src = '';
            if (ticket.receiptUrl) {
                modalReceipt.src = ticket.receiptUrl;
            }
            
            // Load user info
            modalUserName.textContent = 'Cargando...';
            modalUserEmail.textContent = 'Cargando...';
            modalUserPhone.textContent = 'Cargando...';
            
            if (ticket.userId) {
                database.ref('users/' + ticket.userId).once('value')
                    .then((snapshot) => {
                        const userData = snapshot.val();
                        if (userData) {
                            modalUserName.textContent = userData.name || 'N/A';
                            modalUserEmail.textContent = userData.email || 'N/A';
                            modalUserPhone.textContent = userData.phone || 'N/A';
                        } else {
                            modalUserName.textContent = 'N/A';
                            modalUserEmail.textContent = 'N/A';
                            modalUserPhone.textContent = 'N/A';
                        }
                    });
            } else {
                modalUserName.textContent = 'N/A';
                modalUserEmail.textContent = 'N/A';
                modalUserPhone.textContent = 'N/A';
            }
            
            // Show/hide actions based on status
            if (ticket.status === 'pending') {
                modalActions.style.display = 'flex';
            } else {
                modalActions.style.display = 'none';
            }
            
            // Show modal
            ticketModal.style.display = 'flex';
        }

        // Update ticket status
        function updateTicketStatus(ticketId, status) {
            database.ref('tickets/' + ticketId).update({
                status: status,
                processedBy: currentUser.uid,
                processedAt: firebase.database.ServerValue.TIMESTAMP
            })
            .then(() => {
                alert(`Ticket ${status === 'confirmed' ? 'confirmado' : 'rechazado'} con éxito`);
                ticketModal.style.display = 'none';
            })
            .catch((error) => {
                alert('Error al actualizar el ticket: ' + error.message);
            });
        }

        // Update stats
        function updateStats() {
            totalTickets.textContent = tickets.length;
            confirmedTickets.textContent = tickets.filter(t => t.status === 'confirmed').length;
            pendingTickets.textContent = tickets.filter(t => t.status === 'pending').length;
            rejectedTickets.textContent = tickets.filter(t => t.status === 'rejected').length;
        }

        // Run app
        init();
    </script>
</body>
</html>
