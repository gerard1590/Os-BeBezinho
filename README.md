# Os-BeBezinho
Drareg, Ozne, Ruhtra e Ovatsug
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dar Match</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        #match-container {
            width: 80%;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        #user-list {
            margin-bottom: 20px;
        }
        .user-item {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .user-item button {
            padding: 5px 10px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .user-item button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div id="match-container">
        <h1>Dar Match</h1>
        <div id="user-list"></div>
        <button id="logout-button">Sair</button>
    </div>
    <script>
        const userListDiv = document.getElementById('user-list');
        const logoutButton = document.getElementById('logout-button');

        // Simula uma lista de usuários
        const users = ['user1', 'user2', 'user3']; // Usuários fictícios

        // Obtém o usuário logado
        const loggedInUser = localStorage.getItem('username');

        // Exibe a lista de usuários
        users.forEach(user => {
            if (user !== loggedInUser) {
                const userItem = document.createElement('div');
                userItem.classList.add('user-item');
                userItem.innerHTML = `
                    ${user}
                    <button onclick="giveMatch('${user}')">Dar Match</button>
                `;
                userListDiv.appendChild(userItem);
            }
        });

        // Função para dar match
        function giveMatch(user) {
            alert(`Você deu match com ${user}`);
            // Aqui você pode adicionar lógica para armazenar os matches
        }

        // Função de logout
        logoutButton.addEventListener('click', () => {
            localStorage.removeItem('username');
            localStorage.removeItem('password');
            window.location.href = 'login.html'; // Redireciona para a página de login
        });
    </script>
</body>
</html>
