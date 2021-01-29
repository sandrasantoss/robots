# robots
Robot preparado para consultar os valores mensais registados no e-factura, como Comerciante -- VERSÃO 1.0

Notas:
1 - Só funciona com Internet Explorer
2 - Só foi testado em ambiente Windows 103 - Precisa de ter macros activadas4 - Só funciona para 2018/2021

Para funcionar:
- Preencher a coluna 1 com um código de cliente (o robot cria uma folha de excel par acada cliente com esse código), nome apenas para identificação, NIF e Senha da AT
- Eliminar as folhas com os códigos de cliente (estão aqui apenas para exemplo)- Nas células a cor, colocar o ano (o robot está peraparado para consultar informação desde 2018 até 2021, e escolher a opção 0 ou 1, caso se deseje ver o Internet Explorar a abrir e fechar.
- Clicar no botão "Robot"
Os totais mensais são retirados desta página:https://faturas.portaldasfinancas.gov.pt/consultarTotaisMensaisFaturaEmitente.action

Apontamento final:
- Robot simples, feito por mim, não programadora.Tentei acautelar situações de erro e nos casos em que o portal não funcione ou esteja lento. Como está programado em Visual Basic, no caso de ter algum erro, o ficheiro para e aparece uma mansagem com duas opções: End ou Debug. Se escolherem Debug, é mostrada uma página com um apontador amarelo para a linha de código que tem erro
- Não se pode mexer na formatação desta página (por exemplo, as senhas têm de reconhecer 0 à esquerda, se alterar a formatação para número, o 0 desaparece e o login falha)
- A localização onde são colocados os valores é estática, se não houver um ano , vai haver colunas vazias
- As páginas excel com os valores são criadas sem nenhuma formatação, e podem ser trabalhadas com fórmulas
- No caso de haver um mês em que não há ficheiro saft enviado, não é colocada linha com os valores a 0, todas as linhas têm valores
- O código é distribuido em formato aberto, não está protegido com senha e pode ser consultado fazendo ALT+F11
- Está disponível para download na minha conta de github, com indicação da versão, no caso de fazer alterações
sandrasantoss/robots: Robots (github.com)
- Agradeço correções ou sugestões de melhoria
