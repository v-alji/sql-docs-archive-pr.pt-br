---
title: Selecionar as tabelas Oracle para capturar alterações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selOraTabDia
ms.assetid: 2e295dc8-999d-4c4d-96cc-1519674b47a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e9064789dce83ff7d3917ed026c861743142e048
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683137"
---
# <a name="select-oracle-tables-for-capturing-changes"></a><span data-ttu-id="99c44-102">Selecionar as tabelas Oracle para capturar alterações</span><span class="sxs-lookup"><span data-stu-id="99c44-102">Select Oracle Tables for Capturing Changes</span></span>
  <span data-ttu-id="99c44-103">Use esta caixa de diálogo para selecionar as tabelas incluídas na instância CDC.</span><span class="sxs-lookup"><span data-stu-id="99c44-103">Use this dialog box to select the tables that are included in the CDC instance.</span></span> <span data-ttu-id="99c44-104">As tabelas selecionadas são adicionadas à lista na página **Selecionar Tabelas e Colunas** do Assistente de Nova Instância.</span><span class="sxs-lookup"><span data-stu-id="99c44-104">The tables selected are added to the list in the **Select Tables and Columns** page of the New Instance wizard.</span></span> <span data-ttu-id="99c44-105">É possível fazer o seguinte nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99c44-105">You can do the following in this dialog box.</span></span>  
  
 <span data-ttu-id="99c44-106">Por padrão, nenhuma tabela está incluída na lista de tabelas nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99c44-106">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="99c44-107">Você pode marcar a caixa de seleção na parte superior da coluna de caixa de seleção para selecionar todas as tabelas ou procurar tabelas específicas.</span><span class="sxs-lookup"><span data-stu-id="99c44-107">You can select the check box at the top of the check box column to select all of the tables or search for specific tables.</span></span>  
  
 <span data-ttu-id="99c44-108">**Para pesquisar tabelas específicas**</span><span class="sxs-lookup"><span data-stu-id="99c44-108">**To search for specific tables**</span></span>  
 <span data-ttu-id="99c44-109">Insira os critérios de pesquisa da seguinte maneira e clique em **Pesquisar**:</span><span class="sxs-lookup"><span data-stu-id="99c44-109">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="99c44-110">**Esquema**: selecione um esquema de banco de dados da lista.</span><span class="sxs-lookup"><span data-stu-id="99c44-110">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="99c44-111">Somente tabelas que têm esquema serão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="99c44-111">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="99c44-112">**Padrão de Nome de Tabela**: insira qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99c44-112">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="99c44-113">Somente tabelas que incluem a cadeia de caracteres inserida serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="99c44-113">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99c44-114">Você pode inserir critérios em um ou ambos os campos.</span><span class="sxs-lookup"><span data-stu-id="99c44-114">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="99c44-115">**Exibir as 1000 primeiras tabelas correspondentes**: por padrão, esta caixa de seleção está marcada.</span><span class="sxs-lookup"><span data-stu-id="99c44-115">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="99c44-116">Limita o vídeo às primeiras 1000 tabelas compatíveis.</span><span class="sxs-lookup"><span data-stu-id="99c44-116">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="99c44-117">Se você desmarcar a caixa de seleção, todas as tabelas que correspondem aos critérios serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="99c44-117">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="99c44-118">Se houver um número grande de tabelas, poderá levar muito tempo para exibir a lista.</span><span class="sxs-lookup"><span data-stu-id="99c44-118">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="99c44-119">**Para selecionar tabelas a serem incluídas na instância CDC**</span><span class="sxs-lookup"><span data-stu-id="99c44-119">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="99c44-120">Clique na caixa de seleção ao lado de qualquer uma das tabelas que você quer incluir e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="99c44-120">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="99c44-121">As tabelas são adicionadas à lista na página **Selecionar Tabelas e Colunas** do Assistente de Nova Instância.</span><span class="sxs-lookup"><span data-stu-id="99c44-121">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="99c44-122">Clique em **Fechar** para fechar a caixa de diálogo sem adicionar tabelas.</span><span class="sxs-lookup"><span data-stu-id="99c44-122">Click **Close** to close the dialog box without adding any additional tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99c44-123">Se você selecionar uma tabela que inclui um tipo de dados sem suporte, verá uma mensagem de erro e a tabela não será incluída.</span><span class="sxs-lookup"><span data-stu-id="99c44-123">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c44-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99c44-124">See Also</span></span>  
 <span data-ttu-id="99c44-125">[Como criar a instância de banco de dados de alteração do SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="99c44-125">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="99c44-126">Selecionar tabelas e colunas Oracle</span><span class="sxs-lookup"><span data-stu-id="99c44-126">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
