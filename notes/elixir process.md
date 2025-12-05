---
created: 2025-02-14T15:07
updated: 2025-12-05T14:32
---
#languages/elixir 
spawn a process
```exs
pid = spawn (fn ->
  receive do
    {：msg, contents} -> I0.puts (contents)
  end
end
```

send a message to a process
```exs
send(pid, {:msg, "Hello, World!"})
```