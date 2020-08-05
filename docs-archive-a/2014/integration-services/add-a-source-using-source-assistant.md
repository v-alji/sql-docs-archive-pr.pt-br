---
title: Adicionar uma fonte usando o assistente de origem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b58b10508765580e0cffe9bd62099f3e2d69863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573265"
---
# <a name="add-a-source-using-source-assistant"></a><span data-ttu-id="10f17-102">Adicionar uma origem com o Assistente de Origem</span><span class="sxs-lookup"><span data-stu-id="10f17-102">Add a Source using Source Assistant</span></span>
  <span data-ttu-id="10f17-103">Este tópico fornece etapas para adicionar uma nova origem por meio do Assistente de Origem e também lista as opções que estão disponíveis na caixa de diálogo **Adicionar Nova Origem** que você verá ao arrastar-soltar o Assistente de Origem para o Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="10f17-103">This topic provides steps to add a new source using the Source Assistant and also lists the options that are available on the **Add New Source** dialog, which you will see when you drag-drop the Source Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-source-assistant-to-add-a-source"></a><span data-ttu-id="10f17-104">Para usar o Assistente de Origem para adicionar uma origem</span><span class="sxs-lookup"><span data-stu-id="10f17-104">To use Source Assistant to add a source</span></span>  
  
1.  <span data-ttu-id="10f17-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ao qual você deseja adicionar um componente de origem.</span><span class="sxs-lookup"><span data-stu-id="10f17-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a source component to.</span></span>  
  
2.  <span data-ttu-id="10f17-106">Arraste o componente **Assistente de Origem** da Caixa de Ferramentas do SSIS para a guia **Fluxo de Dados** . Você deveria ver a caixa de diálogo **Adicionar Nova Origem** .</span><span class="sxs-lookup"><span data-stu-id="10f17-106">Drag the **Source Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Source** dialog box.</span></span> <span data-ttu-id="10f17-107">A próxima seção fornece detalhes sobre as opções disponíveis na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10f17-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="10f17-108">Selecione o tipo do destino na lista **Tipos**.</span><span class="sxs-lookup"><span data-stu-id="10f17-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="10f17-109">Selecione um gerenciador de conexões na lista **Gerenciadores de Conexões** ou selecione **\<New>** para criar um.</span><span class="sxs-lookup"><span data-stu-id="10f17-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="10f17-110">Se você selecionar um gerenciador de conexões existente, clique em **OK** para fechar a caixa de diálogo **Adicionar Novo Destino**.</span><span class="sxs-lookup"><span data-stu-id="10f17-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="10f17-111">Você deve ver o destino e os gerenciadores de conexões adicionados ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="10f17-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="10f17-112">Se clicar em **\<New>** para criar um gerenciador de conexões, você verá uma caixa de diálogo **Gerenciador de Conexões**, que permite especificar parâmetros para a conexão.</span><span class="sxs-lookup"><span data-stu-id="10f17-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="10f17-113">Depois de concluir a criação do novo gerenciador de conexões, você verá o destino e o gerenciador de conexões no Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="10f17-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
