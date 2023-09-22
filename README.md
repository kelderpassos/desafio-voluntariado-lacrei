
# Desafio DevSecOps para voluntariado na Lacrei!

Desenvolver uma esteira de verificação de segurança de código do repositório https://github.com/frol/flask-restplus-server-example utilizando a ferramenta Bandit juntamente com outra de SAST à minha escolha.


  
## Explicação
Dentro do desenvolvimento de aplicações, é importante sempre levar em consideração o seu nível de segurança para que o risco de potenciais de ataques hacker sejam mitigados. Para tal, através do Github Actions é possível criar uma esteira de trabalhos, onde avaliadores de segurança de código são rodados para inspecionar o código presente num repositório sempre que este é atualizado de alguma forma (push e PR's por exemplo).

Neste desafio, implementei dois trabalhos deste tipo utilizando duas ferramentas diferentes, Bandit (nativa do Python) e Snyk (ferramenta de código aberto que avalia várias linguagens), que avaliam sempre que há push e PR's são abertos antes de serem mergeados. O código onde as ferramentas rodaram em busca de vulnerabilidades foi o repositório https://github.com/frol/flask-restplus-server-example.

Ambas ferramentas encontraram vulnerabilidades de diferentes níveis que fizeram as ações falharem e o PR aberto ser bloqueado para mergeamento. Eis aí uma das grandes funcionalidades desta esteira: ela automatizou o processo de verificação do código e impediu que vulnerabilidades fossem adicionadas à branch principal do projeto (main).

Por mais que Bandit e Snyk possam ser rodadas localmente, a possibilidade de integrá-las a ações no Github permite que nenhuma vulnerabilidades passe sem que ela não seja identificada. No tocante ao Snyk especificamente, é possível acessar sua plataforma oficial e consertar algumas, a depender de sua natureza, diretamente pelo painel disponibilizado. Esta é uma facilidade que ferramentas SCA/SAST são capazes de fornecer e que nativas, como o Bandit, não: é possível gerenciar os vários repositórios de diferentes projetos numa única tela ou sistema aumentando assim a produtividade e capacidade de gerenciamento de equipes DevSecOps. Além disso, há também como receber ajuda através do suporte técnico para resolver problemas de implementação (fator que foi fundamental para a implantação do Snyk dentro da esteira deste desafio, de modo que ele executasse a análise do código bem sucedidamente).

Um último ponto a destacar é fato de cada ferramenta ter apresentado resultados diferentes: enquanto Bandit encontrou 16 vulnerabilidades, 15 baixas e 1 alta severidade, Snyk encontrou 17 sendo 2 de alta, 1 de média e 2 de baixa severidade. Isso mostra que há interseções entre os parâmetros de avaliação, mas que também eles também tem critérios diferentes na hora que qualificar vulnerabilidades, o que faz com que um possa cobrir possíveis deficiências do outro.

## Capturas
### Bandit
![assets/bandit.png](https://github.com/kelderpassos/desafio-voluntariado-lacrei/blob/main/assets/bandit.png)

### Snyk
![assets/bandit.png](https://github.com/kelderpassos/desafio-voluntariado-lacrei/blob/main/assets/snyk.png)


