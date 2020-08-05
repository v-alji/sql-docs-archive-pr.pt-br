---
title: Adicionar um destino usando o assistente de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 747a0de0-3c2f-4d31-a692-7111fc0911d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd36828a7bab7fb33b86765f9f064b6406a17a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570823"
---
# <a name="add-a-destination-using-destination-assistant"></a><span data-ttu-id="23abd-102">Adicionar um destino por meio do Assistente de Destino</span><span class="sxs-lookup"><span data-stu-id="23abd-102">Add a Destination using Destination Assistant</span></span>
  <span data-ttu-id="23abd-103">Este tópico fornece etapas para adicionar um novo destino por meio do Assistente de Destino e também lista as opções que estão disponíveis na caixa de diálogo **Adicionar Novo Destino** que você verá ao arrastar-soltar o Assistente de Destino para o Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="23abd-103">This topic provides steps to add a new destination using the Destination Assistant and also lists the options that are available on the **Add New Destination** dialog, which you will see when you drag-drop the Destination Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-destination-assistant-to-add-a-destination"></a><span data-ttu-id="23abd-104">Para usar o Assistente de Destino para adicionar um destino</span><span class="sxs-lookup"><span data-stu-id="23abd-104">To use Destination Assistant to add a destination</span></span>  
  
1.  <span data-ttu-id="23abd-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ao qual você deseja adicionar um componente de destino.</span><span class="sxs-lookup"><span data-stu-id="23abd-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a destination component to.</span></span>  
  
2.  <span data-ttu-id="23abd-106">Arraste o componente **Assistente de Destino** da Caixa de Ferramentas do SSIS para a guia **Fluxo de Dados** . Você deve ver a caixa de diálogo **Adicionar Novo Destino** .</span><span class="sxs-lookup"><span data-stu-id="23abd-106">Drag the **Destination Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Destination** dialog box.</span></span> <span data-ttu-id="23abd-107">A próxima seção fornece detalhes sobre as opções disponíveis na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23abd-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="23abd-108">Selecione o tipo do destino na lista **Tipos**.</span><span class="sxs-lookup"><span data-stu-id="23abd-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="23abd-109">Selecione um gerenciador de conexões na lista **Gerenciadores de Conexões** ou selecione **\<New>** para criar um.</span><span class="sxs-lookup"><span data-stu-id="23abd-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="23abd-110">Se você selecionar um gerenciador de conexões existente, clique em **OK** para fechar a caixa de diálogo **Adicionar Novo Destino**.</span><span class="sxs-lookup"><span data-stu-id="23abd-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="23abd-111">Você deve ver o destino e os gerenciadores de conexões adicionados ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="23abd-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="23abd-112">Se clicar em **\<New>** para criar um gerenciador de conexões, você verá uma caixa de diálogo **Gerenciador de Conexões**, que permite especificar parâmetros para a conexão.</span><span class="sxs-lookup"><span data-stu-id="23abd-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="23abd-113">Depois de concluir a criação do novo gerenciador de conexões, você verá o destino e o gerenciador de conexões no Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="23abd-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
