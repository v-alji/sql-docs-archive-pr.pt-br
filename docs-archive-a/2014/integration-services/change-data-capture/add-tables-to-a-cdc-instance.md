---
title: Adicionar tabelas a uma instância CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- addTabs
ms.assetid: ad260e19-c021-4035-9311-c02fc96ceaea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: edcd84db9e3c464334d407987cb3567f78edd44e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678938"
---
# <a name="add-tables-to-a-cdc-instance"></a><span data-ttu-id="7c681-102">Adicionar tabelas a uma instância CDC</span><span class="sxs-lookup"><span data-stu-id="7c681-102">Add Tables to a CDC Instance</span></span>
  <span data-ttu-id="7c681-103">Use a caixa de diálogo Seleção de Tabela para adicionar tabelas da origem do Oracle para a instância CDC.</span><span class="sxs-lookup"><span data-stu-id="7c681-103">Use the Table Selection dialog box to add additional tables from the Oracle source to the CDC instance.</span></span> <span data-ttu-id="7c681-104">As tabelas selecionadas são adicionadas à lista na guia **Tabelas** do editor de Propriedades.</span><span class="sxs-lookup"><span data-stu-id="7c681-104">The tables selected are added to the list in the **Tables** tab of the Properties editor.</span></span>  
  
 <span data-ttu-id="7c681-105">Por padrão, nenhuma tabela está incluída na lista de tabelas nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7c681-105">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="7c681-106">Você pode marcar a caixa de seleção **(Selecionar Tudo)** ou pesquisar tabelas específicas.</span><span class="sxs-lookup"><span data-stu-id="7c681-106">You can select the **(Select All)** check box or search for specific tables.</span></span>  
  
 <span data-ttu-id="7c681-107">**Para pesquisar tabelas específicas**</span><span class="sxs-lookup"><span data-stu-id="7c681-107">**To search for specific tables**</span></span>  
 <span data-ttu-id="7c681-108">Insira os critérios de pesquisa da seguinte maneira e clique em **Pesquisar**:</span><span class="sxs-lookup"><span data-stu-id="7c681-108">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="7c681-109">**Esquema**: selecione um esquema de banco de dados da lista.</span><span class="sxs-lookup"><span data-stu-id="7c681-109">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="7c681-110">Somente tabelas que têm esquema serão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="7c681-110">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="7c681-111">**Padrão de Nome de Tabela**: insira qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7c681-111">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="7c681-112">Somente tabelas que incluem a cadeia de caracteres inserida serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="7c681-112">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c681-113">Você pode inserir critérios em um ou ambos os campos.</span><span class="sxs-lookup"><span data-stu-id="7c681-113">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="7c681-114">**Exibir as 1000 primeiras tabelas correspondentes**: por padrão, esta caixa de seleção está marcada.</span><span class="sxs-lookup"><span data-stu-id="7c681-114">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="7c681-115">Limita o vídeo às primeiras 1000 tabelas compatíveis.</span><span class="sxs-lookup"><span data-stu-id="7c681-115">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="7c681-116">Se você desmarcar a caixa de seleção, todas as tabelas que correspondem aos critérios serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="7c681-116">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="7c681-117">Se houver um número grande de tabelas, poderá levar muito tempo para exibir a lista.</span><span class="sxs-lookup"><span data-stu-id="7c681-117">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="7c681-118">**Para selecionar tabelas a serem incluídas na instância CDC**</span><span class="sxs-lookup"><span data-stu-id="7c681-118">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="7c681-119">Clique na caixa de seleção ao lado de qualquer uma das tabelas que você quer incluir e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7c681-119">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="7c681-120">As tabelas são adicionadas à lista na página **Selecionar Tabelas e Colunas** do Assistente de Nova Instância.</span><span class="sxs-lookup"><span data-stu-id="7c681-120">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="7c681-121">Clique em **Fechar** para fechar a caixa de diálogo sem adicionar tabelas.</span><span class="sxs-lookup"><span data-stu-id="7c681-121">Click **Close** to close the dialog box without adding any tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c681-122">Se você selecionar uma tabela que inclui um tipo de dados sem suporte, verá uma mensagem de erro e a tabela não será incluída.</span><span class="sxs-lookup"><span data-stu-id="7c681-122">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c681-123">Você pode exibir a lista de tabelas no visualizador.</span><span class="sxs-lookup"><span data-stu-id="7c681-123">You can view the list of tables in the viewer.</span></span> <span data-ttu-id="7c681-124">Ao usar o visualizador, as informações serão somente leitura.</span><span class="sxs-lookup"><span data-stu-id="7c681-124">When using the viewer the information is read only.</span></span> <span data-ttu-id="7c681-125">O visualizador também inclui uma lista das colunas capturadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="7c681-125">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="7c681-126">Para obter mais informações sobre como acessar o visualizador, consulte [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="7c681-126">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c681-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c681-127">See Also</span></span>  
 <span data-ttu-id="7c681-128">[Como editar as propriedades de instância CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7c681-128">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 <span data-ttu-id="7c681-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="7c681-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="7c681-130">Selecionar as tabelas Oracle para capturar alterações</span><span class="sxs-lookup"><span data-stu-id="7c681-130">Select Oracle Tables for Capturing Changes</span></span>](select-oracle-tables-for-capturing-changes.md)  
  
  
