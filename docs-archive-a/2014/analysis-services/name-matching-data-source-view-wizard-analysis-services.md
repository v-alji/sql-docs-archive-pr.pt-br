---
title: Correspondência de nomes (Assistente de exibição da fonte de dados) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.namematchingcriteria.f1
ms.assetid: 7f811e02-0fe6-45c9-a7b7-29c61032d96b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50cc46db7f582e0aea1570dadc956336ef8be074
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574347"
---
# <a name="name-matching-data-source-view-wizard-analysis-services"></a><span data-ttu-id="1f0d1-102">Correspondência de Nomes (Assistente de Exibição da Fonte de Dados) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="1f0d1-102">Name Matching (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="1f0d1-103">Use a página **Correspondência de Nomes** para selecionar o critério a ser usado para detectar possíveis relações entre as tabelas selecionadas para a exibição da fonte de dados e as outras tabelas no esquema.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-103">Use the **Name Matching** page to select the criterion to use for detecting possible relationships between the tables that you select for the data source view and the other tables in the schema.</span></span> <span data-ttu-id="1f0d1-104">Se não existir nenhuma relação de chave estrangeira entre as tabelas, esse critério ajudará a identificar e adicionar tabelas relacionadas à exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-104">If no physical foreign key relationships exist between the tables, this criterion helps you identify and add related tables to the data source view.</span></span> <span data-ttu-id="1f0d1-105">As relações lógicas identificadas pela correspondência de nomes também são adicionadas à exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-105">The logical relationships that are identified by name matching are also added to the data source view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f0d1-106">Essa página será exibida apenas se você selecionar uma fonte de dados que tem várias tabelas, mas nenhuma relação de chave estrangeira entre qualquer uma da tabelas.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-106">This page appears only if you select a data source that has multiple tables but no foreign key relationships between any one of the tables.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f0d1-107">Opções</span><span class="sxs-lookup"><span data-stu-id="1f0d1-107">Options</span></span>  
 <span data-ttu-id="1f0d1-108">**Criar relações lógicas correspondendo colunas**</span><span class="sxs-lookup"><span data-stu-id="1f0d1-108">**Create logical relationships by matching columns**</span></span>  
 <span data-ttu-id="1f0d1-109">Selecione para usar um critério de correspondência de nomes para detectar possíveis dependências e relações lógicas entre as tabelas que você seleciona para inclusão na exibição da fonte de dados e nas outras tabelas do esquema.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-109">Select to use a name-matching criterion to detect possible logical dependencies and relationships between the tables that you select to include in the data source view and the other tables in the schema.</span></span> <span data-ttu-id="1f0d1-110">Se você desmarcar esta caixa de seleção, nenhum critério de correspondência de nomes será usado para identificar relações lógicas entre tabelas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-110">If you clear this check box, no name-matching criterion is used to identify logical relationships between tables in the data source.</span></span>  
  
 <span data-ttu-id="1f0d1-111">**Correspondências de chave estrangeira**</span><span class="sxs-lookup"><span data-stu-id="1f0d1-111">**Foreign key matches**</span></span>  
 <span data-ttu-id="1f0d1-112">Selecione o critério a ser usado para criar relações lógicas entre tabelas e exibições na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-112">Select the criterion to use for creating logical relationships between tables and views in the data source.</span></span> <span data-ttu-id="1f0d1-113">Caracteres não alfanuméricos são ignorados na correspondência de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-113">Non-alphanumeric characters are ignored in matching strings.</span></span> <span data-ttu-id="1f0d1-114">Por exemplo, todas as cadeias de caracteres "ID de Cliente", "ID_Cliente", "IDCliente" são correspondentes.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-114">For example, "Customer ID", "Customer_ID", "CustomerID" all match.</span></span> <span data-ttu-id="1f0d1-115">Selecione uma das opções na tabela a seguir para criar relações sob as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-115">Select one of the options in the following table to create relationships under the specified conditions.</span></span>  
  
|<span data-ttu-id="1f0d1-116">Selecionar</span><span class="sxs-lookup"><span data-stu-id="1f0d1-116">Select</span></span>|<span data-ttu-id="1f0d1-117">Para criar</span><span class="sxs-lookup"><span data-stu-id="1f0d1-117">To create</span></span>|  
|------------|---------------|  
|<span data-ttu-id="1f0d1-118">**Mesmo nome que a chave primária**</span><span class="sxs-lookup"><span data-stu-id="1f0d1-118">**Same name as primary key**</span></span>|<span data-ttu-id="1f0d1-119">Uma relação lógica com qualquer tabela com um nome de coluna que corresponda ao nome da coluna de chave primária em uma tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-119">A logical relationship to any table with a column name that matches the name of the primary key column in a selected table.</span></span>|  
|<span data-ttu-id="1f0d1-120">**Mesmo nome que a tabela de destino**</span><span class="sxs-lookup"><span data-stu-id="1f0d1-120">**Same name as destination table name**</span></span>|<span data-ttu-id="1f0d1-121">Uma relação lógica com qualquer tabela com um nome de coluna que corresponda ao nome de uma tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-121">A logical relationship to any table with a column name that matches the name of a selected table.</span></span>|  
|<span data-ttu-id="1f0d1-122">**Nome da tabela de destino + nome de chave primária**</span><span class="sxs-lookup"><span data-stu-id="1f0d1-122">**Destination table name + primary key name**</span></span>|<span data-ttu-id="1f0d1-123">Uma relação lógica com qualquer tabela na qual um nome de coluna corresponde ao nome da tabela selecionada concatenado com o nome da coluna de chave primária da tabela selecionada, nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-123">A logical relationship to any table in which a column name matches the selected table name concatenated with the name of the primary key column for the selected table, in that order.</span></span> <span data-ttu-id="1f0d1-124">Caracteres não alfanuméricos dentro da concatenação são ignorados (por exemplo, "ID Produto", "ID_Produto" e "IDProduto", todos correspondem).</span><span class="sxs-lookup"><span data-stu-id="1f0d1-124">Non-alphanumeric characters within the concatenation are ignored (for example, "Product ID", "Product_ID" and "ProductID" all match).</span></span>|  
  
 <span data-ttu-id="1f0d1-125">**Descrição e exemplo**</span><span class="sxs-lookup"><span data-stu-id="1f0d1-125">**Description and sample**</span></span>  
 <span data-ttu-id="1f0d1-126">Exiba uma descrição e um exemplo do critério selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f0d1-126">View a description and a sample of the selected criterion.</span></span>  
  
  
