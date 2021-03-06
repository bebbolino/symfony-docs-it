.. index::
    single: Aiutanti di Console; Aiutante Table

Aiutante Table
==============

.. versionadded:: 2.3
    L'aiutante ``table`` è stato introdotto in Symfony 2.3.

.. caution::

    L'aiutante Table è stato deprecato in Symfony 2.5 e sarà rimosso in
    Symfony 3.0. Si dovrebbe usare ora la classe
    :doc:`Table </components/console/helpers/table>`, che è
    più potente.

Quando si costruisce un'applicazione in console, può essere utile mostrare dati tabulari:

.. image:: /images/components/console/table.png

Per mostrare una tabella, usare :class:`Symfony\\Component\\Console\\Helper\\TableHelper`,
impostando testata e righe, e rendere::

    $table = $this->getHelper('table');
    $table
        ->setHeaders(array('ISBN', 'Titolo', 'Autore'))
        ->setRows(array(
            array('99921-58-10-7', 'La divina commedia', 'Dante Alighieri'),
            array('9971-5-0210-0', 'Racconto di due città', 'Charles Dickens'),
            array('960-425-059-0', 'Il signore degli anelli', 'J. R. R. Tolkien'),
            array('80-902734-1-6', 'Dieci piccoli indiani', 'Agatha Christie'),
        ))
    ;
    $table->render($output);

Si può personalizzare anche il formato della tabella. Ci sono due modi per personalizzare
la resa della tabella: con nomi di formato o personalizzando le opzioni di resa.

Personalizzare il formato della tabella con i nomi di formati
-------------------------------------------------------------

.. versionadded:: 2.4
    Il formato ``TableHelper::LAYOUT_COMPACT`` è stato introdotto in Symfony 2.4.

L'aiutante Table dispone di due formati di tabella preconfigurati:

* ``TableHelper::LAYOUT_DEFAULT``

* ``TableHelper::LAYOUT_BORDERLESS``

* ``TableHelper::LAYOUT_COMPACT``

Si può impostare il formato con il metodo :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setLayout`.

Personalizzare il formato della tabella con le opzioni di resa
--------------------------------------------------------------

Si può anche controllare la resa della tabella impostando i valori delle opzioni di resa:

*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setPaddingChar`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setHorizontalBorderChar`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setVerticalBorderChar`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setCrossingChar`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setCellHeaderFormat`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setCellRowFormat`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setBorderFormat`
*  :method:`Symfony\\Component\\Console\\Helper\\TableHelper::setPadType`
