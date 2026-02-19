let tasks = [];

export default function handler(req, res) {
  if (req.method === "GET") {
    return res.status(200).json(tasks);
  }

  if (req.method === "POST") {
    const { text } = req.body;

    if (!text) {
      return res.status(400).json({ error: "Tarefa vazia" });
    }

    const newTask = {
      id: Date.now(),
      text
    };

    tasks.push(newTask);

    return res.status(200).json(newTask);
  }

  if (req.method === "DELETE") {
    const { id } = req.query;

    tasks = tasks.filter(task => task.id != id);

    return res.status(200).json({ success: true });
  }

  return res.status(405).json({ error: "Método não permitido" });
}
