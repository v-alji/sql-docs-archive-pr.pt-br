---
title: Documentos offline para SQL Server 2014
description: Saiba como instalar a documentação offline para SQL Server 2014. Use o SSMS (SQL Server Management Studio) para exibir o conteúdo offline.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573376"
---
# <a name="install-sql-server-2014-offline-documentation"></a>Instalar a documentação offline do SQL Server 2014

Este artigo descreve como baixar e exibir o conteúdo offline SQL Server 2014. O conteúdo offline permite acessar a documentação sem estar conectado à Internet (embora seja necessário inicialmente uma conexão com a Internet para baixá-lo).

A técnica envolve o uso do menu **ajuda** do SQL Server Management Studio (SSMS) para acessar o utilitário Help Viewer (HlpViewer.exe).

A documentação offline está disponível para versões do SQL Server no intervalo de 2012-2019 e, talvez, para outras versões posteriores também. Embora você possa ver o conteúdo de [versões anteriores online](https://docs.microsoft.com/previous-versions/sql/), uma opção offline fornece um modo conveniente de acessar conteúdo mais antigo.

- [SQL Server 2014](#sql-server-2014-offline-content)
- [SQL Server 2012](#sql-server-2012-offline-content)

Para SQL Server 2016 e versões posteriores, consulte a documentação específica da versão para saber como essas versões manipulam a documentação offline.

## <a name="sql-server-2014-offline-content"></a>Conteúdo offline do SQL Server 2014

> [!IMPORTANT]
> O conteúdo Transact-SQL do SQL 2014 só está disponível offline.

As etapas a seguir explicam como carregar conteúdo offline para o SQL Server 2014.

1. Baixe o conteúdo da [Documentação do produto do Microsoft SQL Server 2014 para ambientes restritos por firewall e proxy](https://www.microsoft.com/download/details.aspx?id=42557) no centro de downloads e salve-o em uma pasta.

2. Descompacte o arquivo para exibir o arquivo *. msha* .

   ![Arquivo de instalação da documentação de Ajuda do SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. No SSMS, selecione **Adicionar e Remover o Conteúdo da Ajuda** no menu Ajuda.

   ![Adicionar e remover conteúdo do Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   O Help Viewer é aberto na guia Gerenciar Conteúdo.

4. Para instalar o conteúdo de ajuda mais recente, escolha **Disco** em Origem da instalação e selecione as reticências (...).

   ![Gerenciar fonte de disco de conteúdo no Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > O caminho do repositório Local na guia Gerenciar Conteúdo mostra o local em que o conteúdo será alocado no computador local. Para alterar o local, selecione **Mover**, insira um caminho de pasta diferente no campo **Para** e selecione **OK**.
   Se a instalação da ajuda falhar após a alteração do caminho do repositório Local, feche e abra novamente o Help Viewer. Verifique se o novo local consta no caminho do repositório Local e tente realizar a instalação novamente.

5. Localize a pasta onde você descompactou o conteúdo. Escolha o arquivo **HelpContentSetup.msha** na pasta e selecione **Abrir**.

   ![Abrir o arquivo setup.msha do conteúdo da ajuda do SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. Digite *sql server 2014* na barra de pesquisa. Depois de ver o conteúdo de 2014 disponível, selecione **Adicionar** ao lado de cada pacote de conteúdo (manual) que você deseja instalar no Help Viewer e escolha **Atualizar**.

   ![Pesquisa de manuais do SQL Server 2014 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Atualização e adição de manuais do SQL Server 2014 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > Se o Visualizador da ajuda congelar (travar) ao adicionar conteúdo, altere a linha cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" no arquivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings para uma data no futuro. Para obter mais informações sobre esse problema, confira [O Visual Studio Help Viewer congela](/visualstudio/welcome-to-visual-studio).

7. Você pode verificar se o conteúdo do SQL Server 2014 foi instalado pesquisando por *sql server 2014* no painel de conteúdo à esquerda.

   ![Manuais do SQL Server 2014 atualizados automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a>Conteúdo offline do SQL Server 2012

As etapas a seguir explicam como carregar conteúdo offline para o SQL Server 2012

1. Baixe o conteúdo da [Documentação do produto do Microsoft SQL Server 2012 para ambientes restritos por firewall e proxy](https://www.microsoft.com/download/details.aspx?id=35750) no centro de downloads e salve-o em uma pasta.

2. Descompacte o arquivo para exibir o arquivo *. msha* .

   ![Arquivo de instalação do conteúdo da Ajuda do SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. No SSMS, selecione **Adicionar e Remover o Conteúdo da Ajuda** no menu Ajuda.

   ![Adicionar e remover conteúdo do Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   O Help Viewer é aberto na guia Gerenciar Conteúdo.

4. Para instalar o conteúdo de ajuda mais recente, escolha **Disco** em Origem da instalação e selecione as reticências (...).

   ![Gerenciar fonte de disco de conteúdo no Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > O caminho do repositório Local na guia Gerenciar Conteúdo mostra o local em que o conteúdo será alocado no computador local. Para alterar o local, selecione **Mover**, insira um caminho de pasta diferente no campo **Para** e selecione **OK**.
   Se a instalação da ajuda falhar após a alteração do caminho do repositório Local, feche e abra novamente o Help Viewer. Verifique se o novo local consta no caminho do repositório Local e tente realizar a instalação novamente.

5. Localize a pasta onde você descompactou o conteúdo. Escolha o arquivo **HelpContentSetup.msha** na pasta e selecione **Abrir**.

   ![Abrir o arquivo setup.msha do conteúdo da ajuda do SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. Digite *sql server 2012* na barra de pesquisa. Depois de ver o conteúdo de 2012 disponível, selecione **Adicionar** ao lado de cada pacote de conteúdo (manual) que você deseja instalar no Help Viewer e escolha **Atualizar**.

   ![Pesquisa de manuais do SQL Server 2012 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Atualização e adição de manuais do SQL Server 2012 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > Se o Visualizador da ajuda congelar (travar) ao adicionar conteúdo, altere a linha cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" no arquivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings para uma data no futuro. Para obter mais informações sobre esse problema, confira [O Visual Studio Help Viewer congela](/visualstudio/welcome-to-visual-studio).

7. Você pode verificar se o conteúdo do SQL Server 2012 foi carregado pesquisando por *sql server 2012* no painel de conteúdo à esquerda.

   ![Documentação do SQL Server 2012 atualizada automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a>Exibir documentação offline

Você pode exibir SQL Server conteúdo da ajuda usando o menu **ajuda** na versão mais recente do SQL Server Management Studio (SSMS).

### <a name="view-offline-help-content-in-ssms"></a>Exibir o conteúdo da ajuda offline no SSMS

Para visualizar a ajuda instalada no SSMS, selecione **Inicializar no Help Viewer** no menu Ajuda, para iniciar o Help Viewer.

   ![Inicializar no Help Viewer](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

O Help Viewer é aberto na guia Gerenciar Conteúdo, com o sumário da Ajuda instalada no painel esquerdo. Selecione os artigos no sumário para exibi-los no painel à direita.

> [!Important]
> Se o painel de conteúdo não estiver visível, selecione Conteúdos na margem esquerda. Selecione o ícone de pino para manter o painel de conteúdo aberto.  

   ![Help Viewer com conteúdo](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
