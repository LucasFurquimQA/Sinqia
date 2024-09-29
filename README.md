# Relatório de Teste de Performance

Este documento descreve os resultados dos testes de performance realizados para avaliar o desempenho da funcionalidade de compra de passagens aplicação <a href="https://www.blazedemo.com/">blazedemo</a>.

## Ferramentas Utilizadas
- **Ferramenta de teste**: JMeter
- **Ambiente de teste**: (Descrever as características do ambiente de execução)
  - **Sistema Operacional**: Windows 11
  - **CPU**: Intel Core i5 11600K 3.91 GHz
  - **Memória RAM**: 32GB
  - **Rede**: 500Mbps
  
## Metodologia de Teste
- **Cenários testados**:
  - SMOKE: Teste realizado com 5 VUs em no periodo de 5 minutos com o objetivo de determinar um plano de teste que fizesse sentido com os critérios de aceite passados pelo solicitante. (Não foi levado em consideração para extração de métricas)
  - LOAD: Teste realizado com 280 VUs no periodo de 30 minutos com rampa de 4 minutos.
  - SPIKE: Teste realizado com 400 VUs no periodo de 30 minutos com rampa de 3 minutos e picos de 1300 VUs mantendo-se por 1 minuto.
  
  - Observações: Em ambos os testes (LOAD e SPIKE) oque foi levado em consideração para a contrução do plano de teste foi a vazão, já que foi o ponto critico menciona pelo solicitante.

  - Ponto de atenção: Não foi possivel ter acesso a nenhum APM para validações de uso de infraestrutura e traces das chamadas e suas integrações já que a solicitação em questão se trata de um cenário fictício.
  
## Resultados

### LOAD:
- **Total de Requisições**: `453.269`
- **Requisições por segundo (RPS Estatisticas)**: `234`
- **Requisições por segundo (RPS Gráfico)**: `256-266`
- **Tempo de Resposta 90pct**: `2 segundos (2007ms)`
- **Porcentagem de Erros**: `0.08`

## Gráficos LOAD Test

![Estatísticas](Teste QA Performance - Sinqia/report/Load/pngs/estatisticas_gerais.jpg)

### SPIKE:
- **Total de Requisições**: `333.394`
- **Requisições por segundo (RPS Estatisticas)**: `182`
- **Requisições por segundo (RPS Gráfico)**: `182-212`
- **Tempo de Resposta 90pct**: `1.7 segundos (1786ms)`
- **Porcentagem de Erros**: `4.24`

## Gráficos SPIKE Test
Se você gerou gráficos de performance, pode anexá-los aqui. Utilize imagens ou links para visualizações.

![Estatísticas](Teste QA Performance - Sinqia/report/Load/pngs/estatisticas_gerais.jpg)

## Conclusões
- O sistema apresentou **boa escalabilidade** com o aumento do número de requisições.
- Identificamos uma **pequena degradação de performance** a partir de 2000 requisições simultâneas.
- Não foram observados erros significativos nos testes realizados.

## Próximos Passos
- **Otimização**: Planejamos otimizar a gestão de memória e aumentar a taxa de transferência.
- **Testes Adicionais**: Executaremos novos testes com cenários mais complexos e maior volume de dados.

