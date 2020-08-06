---
title: 'Tarefa 17: revisando o projeto de limpeza DQS criado pelo pacote SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678360"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a><span data-ttu-id="2b95c-102">Tarefa 17: Examinando o projeto de limpeza do DQS criado pelo pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="2b95c-102">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>
  <span data-ttu-id="2b95c-103">Nesta tarefa, você abrirá o projeto do DQS criado pelo pacote do SSIS no Cliente DQS, analisará os resultados do processo de limpeza e, se desejar, executará a limpeza interativa e exportará os resultados.</span><span class="sxs-lookup"><span data-stu-id="2b95c-103">In this task, you open the DQS project created by the SSIS package in DQS Client, review the results from the cleansing process, and optionally perform interactive cleansing and export the results.</span></span>  
  
1.  <span data-ttu-id="2b95c-104">Iniciar **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="2b95c-104">Launch **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="2b95c-105">Clique em **monitoramento de atividade** no painel **Administração** .</span><span class="sxs-lookup"><span data-stu-id="2b95c-105">Click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
3.  <span data-ttu-id="2b95c-106">Classifique a lista com base na **hora de início da atividade** para ver o registro mais recente.</span><span class="sxs-lookup"><span data-stu-id="2b95c-106">Sort the list based on **Activity Start Time** to see the latest record.</span></span>  
  
4.  <span data-ttu-id="2b95c-107">Observe que você vê um nome do projeto no seguinte formato: **CleanseAndCurate. Cleanse Supplier Data. GUID**.</span><span class="sxs-lookup"><span data-stu-id="2b95c-107">Notice that you see a name of the project in the following format: **CleanseAndCurate.Cleanse Supplier Data.GUID**.</span></span>  
  
     <span data-ttu-id="2b95c-108">![Projeto de Limpeza do DQS criado por pacote do SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Projeto de Limpeza do DQS criado por pacote do SSIS")</span><span class="sxs-lookup"><span data-stu-id="2b95c-108">![DQS Cleansing Project Created by SSIS Package](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "DQS Cleansing Project Created by SSIS Package")</span></span>  
  
5.  <span data-ttu-id="2b95c-109">Observe que o valor no campo **is active** é **ativo**.</span><span class="sxs-lookup"><span data-stu-id="2b95c-109">Notice that the value in the **Is Active** field is **Active**.</span></span>  
  
6.  <span data-ttu-id="2b95c-110">Clique na guia **Profiler** no painel inferior para ver as estatísticas do criador de perfil para a atividade de limpeza que o pacote SSIS realizou.</span><span class="sxs-lookup"><span data-stu-id="2b95c-110">Click **Profiler** tab in the bottom pane to see profiler statistics for the Cleansing activity that the SSIS package performed.</span></span>  
  
7.  <span data-ttu-id="2b95c-111">Clique em **fechar** para fechar a tela de **Administração** .</span><span class="sxs-lookup"><span data-stu-id="2b95c-111">Click **Close** to close the **Administration** screen.</span></span>  
  
8.  <span data-ttu-id="2b95c-112">Na página principal do **cliente do DQS**, clique em **Abrir projeto de qualidade de dados** no painel projetos de qualidade de **dados** .</span><span class="sxs-lookup"><span data-stu-id="2b95c-112">In the main page of **DQS Client**, click **Open Data Quality Project** in the **Data Quality Projects** pane.</span></span>  
  
9. <span data-ttu-id="2b95c-113">Na lista de projetos, selecione o projeto criado pelo componente Limpeza do DQS do SSIS.</span><span class="sxs-lookup"><span data-stu-id="2b95c-113">In the list of projects, select the project created by SSIS DQS Cleansing component.</span></span> <span data-ttu-id="2b95c-114">O nome do projeto deve estar no formato: **CleanseAndCurate. Cleanse Supplier Data. GUID (em cor vermelha)**.</span><span class="sxs-lookup"><span data-stu-id="2b95c-114">The name of the project should be in format:  **CleanseAndCurate.Cleanse Supplier Data.GUID (in red color)**.</span></span> <span data-ttu-id="2b95c-115">Talvez seja necessário classificar a lista com base na coluna **data de criação** e procurar o registro mais recente.</span><span class="sxs-lookup"><span data-stu-id="2b95c-115">You may need to sort the list based on **Date Created** column and look for the latest record.</span></span>  
  
10. <span data-ttu-id="2b95c-116">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2b95c-116">Click **Next**.</span></span>  
  
11. <span data-ttu-id="2b95c-117">A página **gerenciar e exibir resultados** deve ser familiar a você da limpeza interativa que você fez anteriormente neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="2b95c-117">The **Manage and View Results** page should be familiar to you from the interactive cleansing you did earlier in this tutorial.</span></span>  
  
12. <span data-ttu-id="2b95c-118">Revise os resultados da limpeza.</span><span class="sxs-lookup"><span data-stu-id="2b95c-118">Review the cleansing results.</span></span> <span data-ttu-id="2b95c-119">Você também pode executar a limpeza interativa e exportar resultados para um arquivo do Excel ou para um banco de dados na página seguinte.</span><span class="sxs-lookup"><span data-stu-id="2b95c-119">You can also perform interactive cleansing and export results to an Excel file or to a database in the next page.</span></span>  
  
13. <span data-ttu-id="2b95c-120">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2b95c-120">Click **Next**.</span></span> <span data-ttu-id="2b95c-121">Nessa página **Exportar** , você pode exportar os resultados para um arquivo do Excel, um arquivo CSV ou um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="2b95c-121">In this **Export** page, you can export results to an excel file, CSV file, or to a SQL database.</span></span>  
  
14. <span data-ttu-id="2b95c-122">Clique em **concluir** para concluir a atividade.</span><span class="sxs-lookup"><span data-stu-id="2b95c-122">Click **Finish** to finish the activity.</span></span>  
  
15. <span data-ttu-id="2b95c-123">Na página principal do **cliente do DQS**, clique em **monitoramento de atividade** no painel **Administração** .</span><span class="sxs-lookup"><span data-stu-id="2b95c-123">In the main page of **DQS Client**, click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
16. <span data-ttu-id="2b95c-124">Observe que o valor do campo **IsActive** para o projeto é **encerrado** agora.</span><span class="sxs-lookup"><span data-stu-id="2b95c-124">Notice that the value of **IsActive** field for the project is **Ended** now.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="2b95c-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2b95c-125">Next Step</span></span>  
 [<span data-ttu-id="2b95c-126">Conclusão</span><span class="sxs-lookup"><span data-stu-id="2b95c-126">Conclusion</span></span>](../../2014/tutorials/conclusion.md)  
  
  
