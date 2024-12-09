
# Code Review
<span style="display: flex; align-items: center;"> 
  <a href="https://sebraepr.com.br">
    <img src="https://firebasestorage.googleapis.com/v0/b/natureatoz-5286d.appspot.com/o/images%2Fstars.png?alt=media"     
        alt="starline" width="200" height="60">
 </a>
</span>
 
---

> [!NOTE]
> **Processo de Revisão de Código Usando GOGS: Regras e Passo a Passo**
 
### Introdução à Revisão de Código:
A revisão de código é um processo sistemático onde desenvolvedores avaliam o código uns dos outros para garantir qualidade, manutenibilidade e aderência a padrões. Isso ajuda a identificar erros cedo, melhorar a legibilidade e compartilhar conhecimento dentro da equipe.

### Visão Geral do GOGS:
GOGS é um serviço Git auto-hospedado, que oferece uma plataforma leve e rápida para hospedagem de código, incluindo funcionalidades como pull requests e revisões de código.

## Regras para Revisão de Código

1. Consistência e Estilo:
    * Siga as convenções de codificação estabelecidas (nomes de variáveis, indentação, comentários).
    * Garanta que a formatação seja consistente (use linters ou formatadores automáticos. Utilize o PRETTIER).

2. Funcionalidade:
    * Verifique se o código atende aos requisitos especificados na tarefa ou issue.
    * Considere casos de borda e potenciais erros.

3. Desempenho:
    * Garanta o uso de algoritmos eficientes e uso otimizado dos recursos.
    * Evite cálculos desnecessários ou uso excessivo de memória.

4. Segurança:
    * Verifique vulnerabilidades (validação de entradas, autenticação, criptografia).
    * Assegure o tratamento correto de dados sensíveis.

5. Documentação:
    * O código deve ser autoexplicativo, com comentários claros e objetivos quando necessário.
    * Certifique-se de que novas APIs, funções ou módulos estão documentados.

6. Cobertura de Testes:
    * Verifique se testes foram incluídos para novas funcionalidades ou correções.
    * Avalie a qualidade e a abrangência dos casos de teste.
  
  
## Passo a Passo da Revisão de Código com GOGS:
1. Criar um Repositório no GOGS:
    * Faça login no GOGS.
    * Vá até a seção "Novo Repositório."
    * Preencha os detalhes (nome, descrição) e escolha a visibilidade (privado/público).
    * Clique em "Criar Repositório."
      
2. Clonar o Repositório:
    * git clone <url-do-repositorio>
    * Substitua <url-do-repositorio> pela URL exibida na página do repositório no GOGS.
      
3. Enviar Código por uma Branch:
    * Crie uma nova branch para a funcionalidade ou correção:
    * git checkout -b feature/nova-funcionalidade
    * git add .
    * git commit -m "Adiciona nova funcionalidade"
    * git push origin feature/nova-funcionalidade
      
4. Abrir um Pull Request (PR):
    * No GOGS, acesse o repositório.
    * Clique em "Novo Pull Request."
    * Escolha a branch base (geralmente main ou master) e compare com sua branch de funcionalidade.
    * Adicione um título, descrição e comentários relevantes.
    * Envie o PR.
      
5. Revisar o Código:
    * Os membros da equipe receberão uma notificação do PR.
    * Revisores devem:
    * Acessar a seção "Pull Requests" no repositório.
    * Clicar no PR específico.
    * Revisar as mudanças na aba "Arquivos Alterados" (Files Changed).
    * Deixar comentários em linhas específicas ou na seção geral.
      
6. Fornecer Feedback:
    * Use uma linguagem clara e construtiva.
    * Sugira melhorias, destaque boas práticas e faça perguntas quando necessário.
    * Marque problemas críticos que precisam ser resolvidos antes da aprovação.
      
7. Autor Responde ao Feedback:
    * Revise os comentários e faça as alterações necessárias.
    * Envie as atualizações para a mesma branch:
    * git push origin feature/nova-funcionalidade
    * Comente no PR para indicar que as mudanças foram realizadas.
      
8. Aprovação e Mesclagem:
    * Após resolver todos os comentários, os revisores aprovam o PR clicando em "Aprovar."
    * O autor ou revisor pode mesclar o PR usando o botão "Merge" no GOGS.
    * Exclua a branch se não for mais necessária.
      
9. Ações Pós-Mesclagem:
    * Verifique se pipelines de integração contínua (CI), se existentes, passaram com sucesso.
    * Atualize a documentação do projeto, se necessário.
    * Comemore a contribuição bem-sucedida!
    * Melhores Práticas:
    * Mantenha os pull requests pequenos e focados em uma única tarefa.
    * Defina um prazo para revisão (ex.: 24-48 horas).
    * Incentive a comunicação aberta entre autores e revisores.
    * Utilize ferramentas automáticas para análise estática de código sempre que possível.
    * Esse processo estruturado utilizando o GOGS garante uma revisão de código colaborativa, eficiente e que melhora tanto a qualidade do código quanto a coesão da equipe.
 
<img src="https://transparencia.sebrae.com.br/static/media/slogo-azul.97b61ad7.png" alt="Profile Image" width="280" height="150">
