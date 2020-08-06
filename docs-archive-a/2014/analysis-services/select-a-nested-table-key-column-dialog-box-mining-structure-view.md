---
title: Caixa de diálogo Selecionar uma coluna de chave de tabela aninhada (exibição de estrutura de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.structure.addnestedtable.f1
helpviewer_keywords:
- Select a Nested Table Key Column dialog box
ms.assetid: f68b89a7-17df-45f8-ba7f-b458cd9b1ec3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dc524f6913b7be15e87869355515397a3e0b65c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581514"
---
# <a name="select-a-nested-table-key-column-dialog-box-mining-structure-view"></a><span data-ttu-id="155b1-102">Selecione uma caixa de diálogo de coluna de chave de tabela aninhada (exibição de estrutura de mineração)</span><span class="sxs-lookup"><span data-stu-id="155b1-102">Select a Nested Table Key Column Dialog Box (Mining Structure View)</span></span>
  <span data-ttu-id="155b1-103">Use a caixa de diálogo **Selecionar uma Coluna de Chave de Tabela Aninhada** para designar uma coluna que funcionará como chave da nova tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="155b1-103">Use the **Select a Nested Table Key Column** dialog box to designate a column that will act as the key for the new nested table.</span></span> <span data-ttu-id="155b1-104">Quando você sair da caixa de diálogo, uma nova tabela será adicionada para a estrutura de mineração que contém a coluna de chave.</span><span class="sxs-lookup"><span data-stu-id="155b1-104">When you exit the dialog box, a new table is added to the mining structure that contains the designated key column.</span></span> <span data-ttu-id="155b1-105">Você pode adicionar colunas à tabela aninhada clicando com o botão direito na estrutura e selecionando **Adicionar uma Coluna**.</span><span class="sxs-lookup"><span data-stu-id="155b1-105">You can add additional columns to the nested table by right-clicking the structure and selecting **Add a Column**.</span></span> <span data-ttu-id="155b1-106">A caixa de diálogo contém diferentes opções dependendo se você esta trabalhando com um modelo de mineração OLAP ou um modelo de mineração relacional.</span><span class="sxs-lookup"><span data-stu-id="155b1-106">The dialog box contains different options depending on whether you are working with an OLAP mining model or a relational mining model.</span></span>  
  
## <a name="options"></a><span data-ttu-id="155b1-107">Opções</span><span class="sxs-lookup"><span data-stu-id="155b1-107">Options</span></span>  
 <span data-ttu-id="155b1-108">**Tabela de origem**</span><span class="sxs-lookup"><span data-stu-id="155b1-108">**Source table**</span></span>  
 <span data-ttu-id="155b1-109">A tabela na qual o modelo de mineração esta baseado.</span><span class="sxs-lookup"><span data-stu-id="155b1-109">The table on which the mining model is based.</span></span>  
  
 <span data-ttu-id="155b1-110">Isto só é usado para modelos de mineração relacionais.</span><span class="sxs-lookup"><span data-stu-id="155b1-110">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="155b1-111">**Coluna de origem**</span><span class="sxs-lookup"><span data-stu-id="155b1-111">**Source column**</span></span>  
 <span data-ttu-id="155b1-112">Uma lista de todas as colunas disponíveis na tabela de origem que você pode usar como chave da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="155b1-112">A list of all the available columns in the source table that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="155b1-113">Isto só é usado para modelos de mineração relacionais.</span><span class="sxs-lookup"><span data-stu-id="155b1-113">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="155b1-114">**Mostrar tipos de coluna**</span><span class="sxs-lookup"><span data-stu-id="155b1-114">**Show column types**</span></span>  
 <span data-ttu-id="155b1-115">Uma lista de tipos de dados de coluna disponíveis.</span><span class="sxs-lookup"><span data-stu-id="155b1-115">A list of available column data types.</span></span> <span data-ttu-id="155b1-116">Selecione ou desmarque os tipos de dados para filtrar a lista de colunas em **Coluna de origem**.</span><span class="sxs-lookup"><span data-stu-id="155b1-116">Select or clear data types to filter the list of columns in **Source column**.</span></span> <span data-ttu-id="155b1-117">Só serão mostradas colunas que correspondem aos tipos de dados marcados na lista **Coluna de origem** .</span><span class="sxs-lookup"><span data-stu-id="155b1-117">Only columns that match the checked data types will be shown in the **Source column** list.</span></span>  
  
 <span data-ttu-id="155b1-118">Isto só é usado para modelos de mineração relacionais.</span><span class="sxs-lookup"><span data-stu-id="155b1-118">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="155b1-119">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="155b1-119">**Attributes**</span></span>  
 <span data-ttu-id="155b1-120">Uma lista de atributos que você pode usar como a chave da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="155b1-120">A list of attributes that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="155b1-121">Isto só é usado para modelos de mineração de OLAP.</span><span class="sxs-lookup"><span data-stu-id="155b1-121">This is only used for OLAP mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155b1-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="155b1-122">See Also</span></span>  
 [<span data-ttu-id="155b1-123">Exibição de estrutura de mineração &#40;designer de modelo de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="155b1-123">Mining Structure View &#40;Data Mining Model Designer&#41;</span></span>](mining-structure-view-data-mining-model-designer.md)  
  
  
