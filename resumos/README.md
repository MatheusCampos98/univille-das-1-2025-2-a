# das-1-2025-2-a

--------------------------------------------------
Abstração

É o processo de modelar problemas do mundo real em um sistema, destacando apenas as características essenciais e ignorando detalhes irrelevantes.

Objetivo: facilitar o entendimento, reduzir a complexidade e permitir que o desenvolvedor trabalhe com conceitos mais próximos da lógica do negócio.

Exemplo: em um sistema bancário, ao criar a classe Conta, não é necessário representar cada detalhe físico do cliente, apenas dados relevantes como saldo e operações.

Benefício: aumenta a clareza do código e a flexibilidade para mudanças.

--------------------------------------------------
Ocultamento de Informação (Encapsulamento)

Prática de esconder os detalhes internos da implementação, expondo apenas interfaces ou métodos necessários para uso externo.

Como funciona: atributos privados + métodos de acesso controlados (getters e setters).

Vantagens:

Protege a integridade dos dados.
Reduz o risco de erros ao impedir acesso direto a variáveis internas.
Permite alterar a implementação sem impactar quem utiliza a classe.

Exemplo: uma classe Conta pode permitir operações de depósito e saque, mas não o acesso direto ao saldo.

--------------------------------------------------
Coesão

Mede o quanto os métodos e atributos de uma classe ou módulo estão focados em um único propósito.

Alta coesão: cada classe tem uma única responsabilidade, seguindo o Single Responsibility Principle.

Baixa coesão: a classe realiza tarefas distintas, tornando o código difícil de entender e manter.

Benefícios:

Facilita a reutilização.

Reduz o impacto de mudanças.
Melhora a testabilidade.

--------------------------------------------------
Acoplamento

É o grau de dependência entre módulos, classes ou componentes.

Baixo acoplamento: classes interagem por meio de abstrações ou interfaces → facilita manutenção e evolução.

Alto acoplamento: mudanças em uma classe podem quebrar várias outras.

Boas práticas para reduzir acoplamento:

Uso de interfaces e injeção de dependência.

Seguir o princípio de Dependency Inversion.

Comunicação por eventos ou mensagens.

--------------------------------------------------
SOLID

Conjunto de princípios para criar código limpo, sustentável e flexível:

S – Single Responsibility Principle: uma classe deve ter apenas um motivo para mudar (uma única responsabilidade).

O – Open/Closed Principle: sistemas devem estar abertos para extensão, mas fechados para modificação. Novas funcionalidades devem ser adicionadas sem alterar o código existente.

L – Liskov Substitution Principle: subclasses devem poder substituir a classe base sem alterar o comportamento esperado do sistema.

I – Interface Segregation Principle: interfaces devem ser específicas e pequenas, evitando obrigar classes a implementar métodos que não utilizam.

D – Dependency Inversion Principle: módulos de alto nível devem depender de abstrações, não de implementações concretas.

--------------------------------------------------
Princípio de Demeter (Lei do Menor Conhecimento)

Cada classe deve conhecer e interagir apenas com o que é necessário para executar sua tarefa.

Regras práticas: um método deve chamar apenas métodos da própria classe, de parâmetros recebidos, de objetos criados localmente ou de seus atributos.

Problema evitado: train wrecks (chamadas encadeadas como pedido.getCliente().getEndereco().getCidade()), que aumentam o acoplamento.

--------------------------------------------------
UML (Unified Modeling Language)

Linguagem de modelagem para representar graficamente sistemas e suas interações.

Principais diagramas:

Diagrama de Classes: estrutura e relacionamentos entre classes.

Diagrama de Sequência: ordem de mensagens entre objetos.

Diagrama de Casos de Uso: funcionalidades do sistema e atores envolvidos.

Relacionamentos:

Herança (seta vazada) – uma classe herda de outra.

Associação (seta cheia) – classes se relacionam.

Implementação (seta pontilhada vazada) – uma classe implementa uma interface.

--------------------------------------------------
Arquitetura de Software

Abrange decisões de alto nível sobre a estrutura e organização do sistema.

Características Arquiteturais (Requisitos Não Funcionais): desempenho, escalabilidade, disponibilidade, segurança, manutenibilidade, observabilidade e custo.

Trade-offs: é impossível maximizar todos os atributos simultaneamente (ex.: mais segurança pode reduzir desempenho).

Estilos Arquiteturais:

Monólito, Microsserviços, Serverless, Arquitetura Hexagonal, Event-Driven, etc.

Design vs. Arquitetura:

Arquitetura: visão ampla, decisões estruturais e tecnológicas.

Design: detalhamento técnico da implementação.

--------------------------------------------------
DevOps

Cultura e conjunto de práticas que integram desenvolvimento (Dev) e operações (Ops) para entregar software com mais agilidade e qualidade.

Ciclo DevOps: planejamento → codificação → integração contínua → testes → implantação → monitoramento → feedback.

Benefícios:

Redução do tempo de entrega.

Mais qualidade e confiabilidade.

Automação de builds, testes e deploys (CI/CD).

--------------------------------------------------
Comunicação Assíncrona

Permite a interação entre serviços de forma desacoplada e não bloqueante.

Padrão Publish/Subscribe (Tópicos):

Um publisher envia mensagens para um broker, que as distribui para múltiplos subscribers.

Alta escalabilidade e facilidade de adicionar novos consumidores.

Ex.: RabbitMQ, Kafka, MQTT.

Filas (Queue/FIFO):

Mensagens processadas em ordem de chegada (First In, First Out).

Comunicação ponto-a-ponto (1:1).

Ex.: AWS SQS, Azure Service Bus.

Fan-out: uma mensagem é copiada para vários consumidores em paralelo.

--------------------------------------------------
Débito Técnico

Compromissos ou atalhos tomados durante o desenvolvimento para ganhar velocidade, que geram custo futuro.

Causas: prazos curtos, falta de conhecimento, decisões arquiteturais ruins ou ausência de testes.

Consequências:

Mais bugs.

Dificuldade de manutenção.

Necessidade de reescrita.

Gestão: documentar débitos, priorizar refatorações e reservar tempo em sprints para reduzi-los.