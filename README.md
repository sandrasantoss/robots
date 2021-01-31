# robots
Robot preparado para consultar os valores mensais registados no e-factura, como Comerciante -- VERSÃO 1.1 em 31/01/2021

Alterações feitas:
Alteração no algoritmo para cálculo das bases, só faz o calculo nos casos em que há valores nesse ano --> tem impacto na eficiência, rapidez
Contributo de Rui Antunes --> uma melhoria no algoritmo para seleccionas as colunas comforme o ano
Sugestão de Hugo franco --> espaçar as colunas entre anos, corrigi a localização das colunas
Contributo de Isaura Santos (filho) --> fazer logout antes de quit do IE, tem impacto na qualidade, evita entrar em conflito com novo login por ter as credenciais memorizadas

O que não foi feito:
- pelo facto dos valores estarem registados no site com o formato texto (pex: 999,53 €), para se poderem usar fórmulas e serem tratados como números é preciso retirar os caracteres de texto. A solução que encontrei foi usar conversão com base nas minhas definições regionais, haverá casos em que não irá funcionar. Ainda não encontrei uma alternativa que funcione para todos os casos, mas quem tem problemas com a forma como os números são apresentados pode corrigir desta forma, nos dois locais onde tem a fórmula, módulo "CopiarValoresTotais", e ver se resulta /no meu pc não consigo testar.

Antes: Format(Replace(Replace(Replace(IVA, " €", ""), ".", ""), ",", "."), "##.##0,00")

Depois: Format(Replace(Replace(Replace(IVA, " €", ""), ".", ""), ",", ","), "##,##0.00")

-- Irei divulgar uma versão para pcs com outras definições regionais



Robot preparado para consultar os valores mensais registados no e-factura, como Comerciante -- VERSÃO 1.0 em 29/01/2021

Notas:
1 - Só funciona com Internet Explorer
2 - Só foi testado em ambiente Windows 10
3 - Precisa de ter macros activadas
4 - Só funciona para 2018/2021

Para funcionar:
- Preencher a coluna 1 com um código de cliente (o robot cria uma folha de excel par acada cliente com esse código), nome apenas para identificação, NIF e Senha da AT
- Eliminar as folhas com os códigos de cliente (estão aqui apenas para exemplo)
- Nas células a cor, colocar o ano (o robot está peraparado para consultar informação desde 2018 até 2021, e escolher a opção 0 ou 1, caso se deseje ver o Internet Explorar a abrir e fechar.
- Clicar no botão "Robot"
Os totais mensais são retirados desta página:
https://faturas.portaldasfinancas.gov.pt/consultarTotaisMensaisFaturaEmitente.action

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



