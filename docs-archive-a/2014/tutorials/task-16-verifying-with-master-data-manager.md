---
title: 'Tarefa 16: verificando com Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 57ad9d3e-8f95-4df6-af01-c291ccf49164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d1649582f97e9e08691726745e4ba14b2f8226bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680723"
---
# <a name="task-16-verifying-with-master-data-manager"></a><span data-ttu-id="b07ca-102">Tarefa 16: Verificando com o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="b07ca-102">Task 16: Verifying with Master Data Manager</span></span>
  <span data-ttu-id="b07ca-103">Nesta tarefa, você verificará o status do trabalho em lotes enviado pelo pacote SSIS e verificará se os dados foram carregados no servidor MDS usando o Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="b07ca-103">In this task, you check the status of the batch job submitted by the SSIS package and verify that the data was uploaded to MDS server by using Master Data Manager.</span></span>  
  
1.  <span data-ttu-id="b07ca-104">Iniciar **Master Data Manager** ( `http://localhost/MDS` ).</span><span class="sxs-lookup"><span data-stu-id="b07ca-104">Launch **Master Data Manager** (`http://localhost/MDS`).</span></span> <span data-ttu-id="b07ca-105">Se ele já estiver aberto, clique em **Microsoft SQL Server Master Data Services** na parte superior para alternar para o **Home Page**.</span><span class="sxs-lookup"><span data-stu-id="b07ca-105">If it is already open, click **Microsoft SQL Server Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="b07ca-106">Clique em **Gerenciamento de integração**.</span><span class="sxs-lookup"><span data-stu-id="b07ca-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="b07ca-107">Observe que há um lote com o nome **EIMBatch** que você enviou na lista.</span><span class="sxs-lookup"><span data-stu-id="b07ca-107">Notice that there is a batch with named **EIMBatch** that you submitted in the list.</span></span> <span data-ttu-id="b07ca-108">Clique em **importar dados** na barra de menus se você não vir a tela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b07ca-108">Click **Import Data** on the menu bar if you do not see the following screen.</span></span>  
  
     <span data-ttu-id="b07ca-109">![Lote EIM](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "Lote EIM")</span><span class="sxs-lookup"><span data-stu-id="b07ca-109">![EIM Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM Batch")</span></span>  
  
4.  <span data-ttu-id="b07ca-110">Volte para a home page clicando em **SQL Server 2012 Master Data Services** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="b07ca-110">Switch back to the home page by click **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
5.  <span data-ttu-id="b07ca-111">Verifique se modelo de **fornecedores** está selecionado para **modelo** e **VERSION_1** está selecionado para **versão**e clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="b07ca-111">Make sure that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**, and click **Explorer**.</span></span>  
  
6.  <span data-ttu-id="b07ca-112">Você pode consultar o pacote SSIS de dados importado para o MDS.</span><span class="sxs-lookup"><span data-stu-id="b07ca-112">You can see the data SSIS package imported into MDS.</span></span> <span data-ttu-id="b07ca-113">Os dados devem ser limpos e não têm valores de **código** de duplicatas (Observação: a coluna **CódigoDoFornecedor** no Excel corresponde ao atributo de **código** da entidade fornecedor no MDS).</span><span class="sxs-lookup"><span data-stu-id="b07ca-113">The data should be cleansed and have no duplicates **Code** values (Note: **SupplierID** column in Excel corresponds to **Code** attribute of Supplier entity in MDS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b07ca-114">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b07ca-114">Next Step</span></span>  
 [<span data-ttu-id="b07ca-115">Tarefa 17: Examinando o projeto de limpeza do DQS criado pelo pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="b07ca-115">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>](../../2014/tutorials/task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package.md)  
  
  
