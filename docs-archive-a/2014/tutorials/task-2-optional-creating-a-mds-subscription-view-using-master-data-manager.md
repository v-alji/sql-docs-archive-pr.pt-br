---
title: 'Tarefa 2 (opcional): criando uma exibição de assinatura do MDS usando Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3da8219-e0cb-4848-95ca-285a76ec1ba9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 998436734ba5c3cf09cfe88f266a0908c0550abc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683181"
---
# <a name="task-2-optional-creating-a-mds-subscription-view-using-master-data-manager"></a><span data-ttu-id="cd8fd-102">Tarefa 2 (opcional): Criando uma exibição de assinatura do MDS usando o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="cd8fd-102">Task 2 (Optional): Creating a MDS Subscription View using Master Data Manager</span></span>
  <span data-ttu-id="cd8fd-103">Nesta tarefa, você cria uma exibição de assinatura para expor a entidade **Supplier** no modelo **suppliers** para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-103">In this task, you create a subscription view to expose the **Supplier** entity in the **Suppliers** model to other applications.</span></span> <span data-ttu-id="cd8fd-104">Você não utiliza essa exibição na versão atual do tutorial.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-104">You do not consume this view in the current version of the tutorial.</span></span>  
  
1.  <span data-ttu-id="cd8fd-105">Alterne para a página principal do **Master Data Manager** ( `http://localhost/MDS` ) clicando em **SQL Server 2012 Master Data Services** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-105">Switch to the main page of **Master Data Manager** (`http://localhost/MDS`) by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
2.  <span data-ttu-id="cd8fd-106">Clique em **Gerenciamento de integração**.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="cd8fd-107">Clique em **criar modos de exibição** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-107">Click **Create Views** on the menu bar.</span></span>  
  
     <span data-ttu-id="cd8fd-108">![Botão Adicionar uma Nova Exibição de Assinatura](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Botão Adicionar uma Nova Exibição de Assinatura")</span><span class="sxs-lookup"><span data-stu-id="cd8fd-108">![Add a New Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Add a New Subscription View Button")</span></span>  
  
4.  <span data-ttu-id="cd8fd-109">Clique no ícone **+ (mais)** na barra de ferramentas para criar uma exibição de assinatura.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-109">Click **+ (Plus)** icon on the toolbar to create a subscription view.</span></span>  
  
5.  <span data-ttu-id="cd8fd-110">No painel **criar exibição de assinatura** , digite **fornecedores** para **nome de exibição de assinatura**.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-110">In the **Create Subscription View** pane, type **Suppliers** for **Subscription view name**.</span></span>  
  
6.  <span data-ttu-id="cd8fd-111">Selecione **Fornecedores** como **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-111">Select **Suppliers** for **Model**.</span></span>  
  
7.  <span data-ttu-id="cd8fd-112">Selecione **VERSION_1** como **Versão**.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-112">Select **VERSION_1** for **Version**.</span></span>  
  
8.  <span data-ttu-id="cd8fd-113">Selecione **fornecedor** para **entidade**.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-113">Select **Supplier** for **Entity**.</span></span>  
  
9. <span data-ttu-id="cd8fd-114">Selecione **membros folha** para o **formato**.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-114">Select **Leaf members** for **Format**.</span></span>  
  
     <span data-ttu-id="cd8fd-115">![Botão Salvar Exibição de Assinatura](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Botão Salvar Exibição de Assinatura")</span><span class="sxs-lookup"><span data-stu-id="cd8fd-115">![Save Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Save Subscription View Button")</span></span>  
  
10. <span data-ttu-id="cd8fd-116">Clique em **salvar** na barra de ferramentas para salvar a exibição de assinatura.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-116">Click **Save** on the toolbar to save the subscription view.</span></span> <span data-ttu-id="cd8fd-117">Essa ação cria uma exibição em SQL Server **fornecedores**nomeados.</span><span class="sxs-lookup"><span data-stu-id="cd8fd-117">This action creates a view in SQL Server named **Suppliers**.</span></span> <span data-ttu-id="cd8fd-118">Você pode verificar isso usando o SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="cd8fd-118">You can verify this using SQL Server Management Studio (SSMS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="cd8fd-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cd8fd-119">Next Step</span></span>  
 [<span data-ttu-id="cd8fd-120">Tarefa 3 &#40;&#41; opcional: revisando as exibições de assinatura</span><span class="sxs-lookup"><span data-stu-id="cd8fd-120">Task 3 &#40;Optional&#41;: Reviewing the Subscription Views</span></span>](task-3-optional-reviewing-the-subscription-views.md)  
  
  
