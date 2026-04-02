
// SORT + FILTER
app.get("/students", (req, res) => {
  let { sort, dept } = req.query;

  let sql = "SELECT * FROM students";

  if (dept) {
    sql += ` WHERE department='${dept}'`;
  }

  if (sort) {
    sql += ` ORDER BY ${sort}`;
  }

  db.query(sql, (err, result) => {
    if (err) throw err;
    res.json(result);
  });
});

// COUNT
app.get("/count", (req, res) => {
  const sql = "SELECT department, COUNT(*) as count FROM students GROUP BY department";

  db.query(sql, (err, result) => {
    if (err) throw err;
    res.json(result);
  });
});
