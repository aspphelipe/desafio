# Clone Digital Eugene Schwartz

Workflow n8n para análise automatizada de copywriting baseado na metodologia de Eugene Schwartz do livro "Breakthrough Advertising" (1966).

## 📋 Sobre o Projeto

Este sistema automatiza a análise de leads de copywriting utilizando os princípios fundamentais de Eugene Schwartz:

- **Identificação do Nível de Consciência** (5 níveis: Unaware → Most Aware)
- **Dissecação de Frameworks** de copywriting utilizados
- **Geração de Novos Ângulos** de marketing
- **Análise e Melhorias** baseadas nos princípios de Schwartz

## 🚀 Como Usar

### Pré-requisitos

- **n8n** instalado e configurado
- **Credenciais OpenAI** (testado com GPT-4 e GPT-4 mini)
- Acesso à API da OpenAI

### Instalação

1. **Importe o workflow** para seu n8n:
   - Copie o conteúdo do arquivo `WORKFLOW DESAFIO.json`
   - No n8n, vá em **Import** e cole o código

2. **Configure as credenciais OpenAI**:
   - Adicione suas credenciais da OpenAI em todos os nós que utilizam o modelo
   - Certifique-se de ter acesso aos modelos GPT-4/GPT-4 mini

3. **Insira sua lead para análise**:
   - Edite o nó "LEAD AQUI"
   - Substitua o texto de exemplo pela sua lead

4. **Execute o workflow**:
   - Clique em "TESTAR SISTEMA" para iniciar a análise

### Entrada Esperada

O sistema espera uma **lead de copywriting** (abertura de sales letter/VSL) como entrada. Exemplo:

```
"Na noite do ano de 1785, Antoine Lavoisier, um químico brilhante e famoso, descobriu o caminho para emagrecer sem sacrifícios..."
```

### Saída do Sistema

O workflow retorna uma análise completa contendo:

- **Nível de Consciência** identificado (1-5)
- **Framework** utilizado na lead
- **Novos Ângulos** sugeridos para diferentes níveis de consciência
- **5 Melhorias específicas** baseadas na metodologia Schwartz

## 🔧 Arquitetura do Sistema

O workflow é composto por **4 agentes especializados**:

### 1. Análise de Nível de Consciência
- **Input:** Lead original
- **Output:** Nível identificado (1-5) + justificativa
- **Base:** Metodologia original de Schwartz (1966)

### 2. Dissecação de Framework
- **Input:** Lead original
- **Output:** Framework identificado + análise estrutural
- **Foco:** Arquitetura persuasiva da lead

### 3. Novos Ângulos
- **Input:** Lead + Nível de consciência identificado
- **Output:** 5 ângulos diferentes para diversos níveis
- **Base:** Técnicas de criação de headlines de Schwartz

### 4. Análise Schwartz
- **Input:** Lead + Framework + Nível + Novos ângulos
- **Output:** 5 pontos de melhoria específicos
- **Metodologia:** Princípios fundamentais de Schwartz

## ⚡ Decisões Técnicas

### Contextos Especializados vs Base Vetorial

Optamos por **contextos especializados** nos prompts ao invés de base vetorial porque:

- ✅ **Aplicação determinística** de metodologias específicas
- ✅ **Conhecimento hierárquico** estruturado (5 níveis → frameworks)
- ✅ **Acesso preciso** a regras condicionais

### Limitações Identificadas

- **Inconsistência** na identificação do nível de consciência (alternância entre níveis 3 e 4)
- **Necessidade de ajuste** nos critérios de análise para maior precisão
- **Falta de swipe file** vetorizado para capturar nuances e formatos de escrita

## 🔄 Melhorias para Produção

### Otimizações Recomendadas

1. **Paralelização com RabbitMQ:**
   - Filas independentes para cada agente
   - Execução simultânea onde possível
   - Retry automático em falhas de API

2. **Base Vetorial Complementar:**
   - Swipe file de leads por nicho
   - Exemplos de headlines eficazes
   - Padrões de frameworks otimizados

3. **Melhoria nos Prompts:**
   - Critérios mais específicos de análise
   - Validação cruzada entre agentes
   - Contextos mais efetivos

## 🧪 Validação e Testes

### Modelos Testados
- ✅ **OpenAI GPT-4** - Mais consistente nos testes
- ✅ **OpenAI GPT-4 mini** - Performance adequada

### Problemas Identificados
- **Inconsistência na identificação** do nível de consciência
- **Alternância entre níveis 3 e 4** para a mesma lead
- **Necessidade de critérios mais específicos** de análise

### Assistente Pinecone
Utilizamos o assistente Pinecone como base vetorial para estudar a metodologia. Para testar:
1. Faça perguntas certas sobre os princípios de Schwartz
2. Incentive o agente a trazer as bases da metodologia
3. Itere com outras ferramentas para formatar prompts

#### 🛠️ Tutorial de Acesso ao Assistente Pinecone

**Passo 1: Criar uma Conta no Pinecone**
1. Acesse [pinecone.io](https://pinecone.io)
2. Faça o cadastro gratuito

**Passo 2: Criar um Pinecone Assistant**
1. No painel do Pinecone, crie um novo assistant
2. Faça o upload dos arquivos que deseja incluir na base de conhecimento
3. Configure o assistant com o conteúdo do livro "Breakthrough Advertising"

**Observação:** Para extrair a metodologia do Schwartz através do assistente, faça uma cadeia de perguntas estratégicas que incentivem o agente a trazer as bases da metodologia completa.

## 📊 Resultados Esperados

Após a análise, você receberá:

- **Diagnóstico preciso** do nível de consciência da lead
- **Identificação do framework** utilizado e sua eficácia
- **5 ângulos alternativos** para diferentes públicos
- **Plano de otimização** com melhorias específicas
- **Exemplos reescritos** aplicando correções

## 🔗 Recursos Adicionais

- [Eugene Schwartz - Breakthrough Advertising](https://example.com)
- [Documentação n8n](https://docs.n8n.io)
- [OpenAI API Documentation](https://platform.openai.com/docs)

## 📝 Licença

Este projeto é de uso educacional baseado na metodologia pública de Eugene Schwartz.

---

**Nota:** Este é um MVP funcional. Para uso em produção, implemente as melhorias sugeridas na seção de otimizações.
