<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/sortablejs@1.14.0/Sortable.min.css" />
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f4f4f4;
    }

    .card-container {
      list-style: none;
      padding: 0;
    }

    .card {
      width: 100%;
      margin: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      padding: 16px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      text-align: center;
      cursor: pointer;
      transition: transform 0.2s ease-in-out;
    }

    .card:hover {
      cursor: grab;
    }

    .card-dragged {
      cursor: grabbing;
    }

    .sortable-ghost {
      opacity: 0.5;
      transform: scale(1.05);
    }

    h2 {
      color: #333;
      margin: 0;
    }

    p {
      color: #666;
    }

    button {
      background-color: #007BFF;
      color: #fff;
      padding: 8px 16px;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
  </style>
  <title>Draggable Cards</title>
</head>
<body>

  <ul class="card-container" id="sortable-list">
    <li class="card">
      <h2>Card 1</h2>
      <p>This is the content of card 1.</p>
      <button>Learn More</button>
    </li>

    <li class="card">
      <h2>Card 2</h2>
      <p>This is the content of card 2.</p>
      <button>Learn More</button>
    </li>

    <li class="card">
      <h2>Card 3</h2>
      <p>This is the content of card 3.</p>
      <button>Learn More</button>
    </li>
  </ul>

  <script src="https://unpkg.com/sortablejs@1.14.0/Sortable.min.js"></script>
  <script>
    new Sortable(document.getElementById('sortable-list'), {
      animation: 150,
      onStart: (evt) => {
        evt.from.classList.add('card-dragged');
      },
      onEnd: (evt) => {
        evt.from.classList.remove('card-dragged');
      }
    });
  </script>

</body>
</html>
