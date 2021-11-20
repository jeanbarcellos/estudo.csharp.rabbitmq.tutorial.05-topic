Repositório somente para estudos!

## RabbitMQ Tutorials: Routing

Receiving messages selectively

Links:

- https://www.rabbitmq.com/tutorials/tutorial-five-dotnet.html

<br>
<br>

### Run the following examples:

Para receber todos os logs:

```
cd ReceiveLogsTopic
dotnet run "#"
```

Para receber todos os logs da instalação `kern`:

```
cd ReceiveLogsTopic
dotnet run "kern.*"
```

Receber somente logs do tipo `critical`:

```
cd ReceiveLogsTopic
dotnet run "*.critical"
```

Criar várias ligações/bindings:

```
cd ReceiveLogsTopic
dotnet run "kern.*" "*.critical"
```

<br>

Para emitir um log com uma chave de roteamento do tipo `kern.critical`:

```
cd EmitLogTopic

dotnet run "kern.critical" "A critical kernel error"

dotnet run "kern.warn" "A warn kernel error"

dotnet run "service.critial" "A critical service error"

```
