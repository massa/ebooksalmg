Hoje, o [Portal da ALMG](http://www.almg.gov.br/) disponibiliza para o
cidadão, na [página de consultas de
legislação](http://www.almg.gov.br/consulte/legislacao/index.html),
quatro livros eletrônicos em formato PDF (com algumas variações no
conteúdo):

1.  [A Constituição Federal de
    1988](http://www.planalto.gov.br/ccivil_03/constituicao/ConstituicaoCompilado.htm);
2.  [<http://www.almg.gov.br/consulte/legislacao/completa/completa-nova-min.html?tipo=CON&num=1989&comp>=&ano=1989&texto=consolidado\#texto
    A Constituição Estadual de 1989];
3.  [<http://www.almg.gov.br/consulte/legislacao/completa/completa-nova-min.html?tipo=LEI&num=869&comp>=&ano=1952&texto=consolidado\#texto
    O Estatuto do Servidor Público de MG];
4.  [<http://www.almg.gov.br/consulte/legislacao/completa/completa-nova-min.html?tipo=RAL&num=5176&comp>=&ano=1997&texto=consolidado\#texto
    O Regimento Interno da ALMG].

Entretanto, verificou-se que o formato PDF não é o mais adequado para os
atuais dispositivos móveis como *smartphones*, *tablets*, e leitores de
*e-books*. Assim, foi feito um programa em Perl que extrai os arquivos
HTML dos links acima, os processa, e transforma em *e-books*, nos
formatos EPUB (que pode ser utilizado no *software* Apple iBooks, nos
leitores de *e-books* das livrarias Saraiva e Leitura, e no leitor de
*e-books* do Google Play, entre outros) e MOBI (que pode ser utilizado
nos leitores Amazon Kindle e no *software* Kindle para as plataformas
iOS e Android, entre outras), além de gerar um arquivo HTML próprio para
ser utilizado em dispositivos móveis com a tela pequena.

Os arquivos gerados foram encaminhados à GDI, para publicação, e à GGov,
para referência.

Esses arquivos podem ser regerados a qualquer momento, sob demanda, no
computador `e4953` ([Usuário:Massa](Usuário:Massa "wikilink")), onde o
programa está instalado.

O ambiente onde roda esse programa (chamado "`gera-ebooks-almg`"), aqui
documentado, não é simples de ser replicado. Ele exige a plataforma
Linux, além da instalação dos seguintes pacotes de software:

1.  [Calibre](http://calibre-ebook.com/): um programa para organizar
    *e-books*, que contém um subprograma que faz a conversão entre
    diversos formatos existentes;
2.  [wget](http://www.gnu.org/software/wget/): um programa para fazer
    acesso à rede e fazer o download dos arquivos HTML;
3.  [HTML Tidy](http://tidy.sourceforge.net/): um programa para "limpar"
    e "padronizar" o HTML que foi baixado, para facilitar o
    processamento posterior;
4.  A versão do Perl utilizada foi a 5.19, e nenhuma outra versão foi
    testada ou homologada.

É feito extenso uso de expressões regulares para processar cada arquivo
HTML.

O processamento de
customização do HTML é feito pelas expressões regulares que se encontram
na função `transformacao_html_almg_e_planalto`.

