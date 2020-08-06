---
title: 'Tarefa 9: Configurando um serviço de dados de referência | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d0535fce-2bf5-4f6d-b517-ffe6fa13738d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1e7c685de13a2f5c495482f816818ff6b838fc7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685968"
---
# <a name="task-9-configuring-a-reference-data-service"></a><span data-ttu-id="eeba1-102">Tarefa 9: Configurando um serviço de dados de referência</span><span class="sxs-lookup"><span data-stu-id="eeba1-102">Task 9: Configuring a Reference Data Service</span></span>
  <span data-ttu-id="eeba1-103">Nesta tarefa, você configura o DQS para usar um serviço de dados de referência no Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="eeba1-103">In this task, you configure DQS to use a Reference Data Service on Azure Marketplace.</span></span> <span data-ttu-id="eeba1-104">Na próxima tarefa, você configurará o domínio de **validação de endereço** para usar esse serviço.</span><span class="sxs-lookup"><span data-stu-id="eeba1-104">In the next task, you will configure the **Address Validation** domain to use this service.</span></span> <span data-ttu-id="eeba1-105">No tempo de execução, durante a atividade de limpeza, o DQS passa os valores dos domínios no domínio de **validação de endereço** para o serviço para limpeza.</span><span class="sxs-lookup"><span data-stu-id="eeba1-105">At runtime, during cleansing activity, DQS passes the values of domains in the **Address Validation** domain to the service for cleansing.</span></span> <span data-ttu-id="eeba1-106">Consulte [Configurar o DQS para usar dados de referência](https://msdn.microsoft.com/library/hh213070.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="eeba1-106">See [Configure DQS to Use Reference Data](https://msdn.microsoft.com/library/hh213070.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="eeba1-107">Na página principal do **cliente do DQS**, no painel **Administração** , clique em **configuração**.</span><span class="sxs-lookup"><span data-stu-id="eeba1-107">In the main page of **DQS Client**, in the **Administration** pane, click **Configuration**.</span></span>  
  
2.  <span data-ttu-id="eeba1-108">Verifique se a guia **dados de referência** está ativa.</span><span class="sxs-lookup"><span data-stu-id="eeba1-108">Ensure that **Reference Data** tab is active.</span></span>  
  
3.  <span data-ttu-id="eeba1-109">Na área **configurações de rede** , digite os valores apropriados nos campos **servidor proxy** e **porta** se você precisar usar um servidor proxy para se conectar à Internet.</span><span class="sxs-lookup"><span data-stu-id="eeba1-109">In the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** fields if you need to use a proxy server to connect to Internet.</span></span>  
  
4.  <span data-ttu-id="eeba1-110">Digite sua **chave de conta do Azure Marketplace** para o campo **ID da conta do DataMarket** .</span><span class="sxs-lookup"><span data-stu-id="eeba1-110">Type your **Azure Marketplace Account Key** for the **DataMarket Account ID** field.</span></span>  
  
     <span data-ttu-id="eeba1-111">![Conta do Serviço de Dados de Referência do Azure Data Market](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Conta do Serviço de Dados de Referência do Azure Data Market")</span><span class="sxs-lookup"><span data-stu-id="eeba1-111">![Azure Data Market Reference Data Service Account](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Azure Data Market Reference Data Service Account")</span></span>  
  
5.  <span data-ttu-id="eeba1-112">Clique no botão **validar** ao lado da caixa de texto para validar a ID da conta.</span><span class="sxs-lookup"><span data-stu-id="eeba1-112">Click **Validate** button next to the text box to validate the account ID.</span></span>  
  
6.  <span data-ttu-id="eeba1-113">Clique em **OK** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="eeba1-113">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="eeba1-114">Clique em **fechar** na parte inferior da página para alternar para a página principal do cliente do DQS.</span><span class="sxs-lookup"><span data-stu-id="eeba1-114">Click **Close** at the bottom of the page to switch to the main page of DQS Client.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="eeba1-115">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="eeba1-115">Next Task</span></span>  
 [<span data-ttu-id="eeba1-116">Tarefa 10: Configurando o domínio composto para usar o serviço de dados de referência</span><span class="sxs-lookup"><span data-stu-id="eeba1-116">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>](../../2014/tutorials/task-10-configuring-composite-domain-to-use-reference-data-service.md)  
  
  
