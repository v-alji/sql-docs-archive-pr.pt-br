---
title: Definir chaves primárias lógicas em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- removing logical primary keys
- logical primary keys [SQL Server]
- deleting logical primary keys
- data source views [Analysis Services], logical primary keys
ms.assetid: 172bc267-c637-4caa-bf55-0ba198d30b1e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25092e5d754381c572dcdbfc03e5ee0f29c1df24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574391"
---
# <a name="define-logical-primary-keys-in-a-data-source-view-analysis-services"></a><span data-ttu-id="849fc-102">Definir chaves primárias lógicas em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="849fc-102">Define Logical Primary Keys in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="849fc-103">O Assistente de Exibição da Fonte de Dados e o Designer de Exibição da Fonte de Dados definem automaticamente uma chave primária para uma tabela que é adicionada a uma exibição da fonte de dados baseada na tabela do banco de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="849fc-103">The Data Source View Wizard and Data Source View Designer automatically define a primary key for a table that is added to a data source view based on underlying database table.</span></span>  
  
 <span data-ttu-id="849fc-104">De vez em quando, pode ser necessário definir manualmente uma chave primária na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="849fc-104">Occasionally, you may need to manually define a primary key in the data source view.</span></span> <span data-ttu-id="849fc-105">Por exemplo, por questões de desempenho ou design, as tabelas da fonte de dados podem não ter colunas de chave primária definidas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="849fc-105">For example, for performance or design reasons, tables in a data source may not have explicitly defined primary key columns.</span></span> <span data-ttu-id="849fc-106">Consultas nomeadas e exibições também podem omitir a coluna da chave primária de um tabela.</span><span class="sxs-lookup"><span data-stu-id="849fc-106">Named queries and views may also omit the primary key column for a table.</span></span> <span data-ttu-id="849fc-107">Se a tabela, exibição ou consulta nomeada não tiver uma chave primária física definida, é possível definir manualmente uma chave primária lógica na tabela, exibição ou consulta nomeada no Designer de Exibição da Fonte de Dados.</span><span class="sxs-lookup"><span data-stu-id="849fc-107">If a table, view, or named query does not have a physical primary key defined, you can manually define a logical primary key on the table, view or named query in Data Source View Designer.</span></span>  
  
## <a name="set-a-logical-primary-key"></a><span data-ttu-id="849fc-108">Definir uma chave primária lógica</span><span class="sxs-lookup"><span data-stu-id="849fc-108">Set a Logical Primary Key</span></span>  
 <span data-ttu-id="849fc-109">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] requer chaves primárias para identificar com exclusividade os registros de uma tabela, identificar as colunas de chave das tabelas da dimensão e oferecer suporte às relações entre tabelas, exibições e consultas nomeadas.</span><span class="sxs-lookup"><span data-stu-id="849fc-109">Primary keys are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to uniquely identify records in a table, identify key columns in dimension tables and to support relationships between tables, views and named queries.</span></span> <span data-ttu-id="849fc-110">Essas relações são usadas na construção de consultas para recuperar dados e metadados de fontes de dados subjacentes e aproveitar os recursos avançados de business intelligence.</span><span class="sxs-lookup"><span data-stu-id="849fc-110">These relationships are used to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="849fc-111">Qualquer coluna pode ser usada para a chave primária lógica, incluindo um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="849fc-111">Any column can be used for the logical primary key, including a named calculation.</span></span> <span data-ttu-id="849fc-112">Quando você criar uma chave primária lógica, uma restrição exclusiva será criada na exibição da fonte de dados e marcada como restrição de chave primária.</span><span class="sxs-lookup"><span data-stu-id="849fc-112">When you create a logical primary key, a unique constraint is created in the data source view and marked as a primary key constraint.</span></span> <span data-ttu-id="849fc-113">Qualquer outra chave primária lógica especificada na tabela selecionada será excluída.</span><span class="sxs-lookup"><span data-stu-id="849fc-113">Any other existing logical primary key specified in the selected table is deleted.</span></span>  
  
1.  <span data-ttu-id="849fc-114">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados na qual você deseja definir uma chave primária lógica.</span><span class="sxs-lookup"><span data-stu-id="849fc-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to set a logical primary key.</span></span>  
  
2.  <span data-ttu-id="849fc-115">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="849fc-115">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
     <span data-ttu-id="849fc-116">Para localizar uma tabela ou exibição, você pode usar a opção **Localizar tabela** clicando no menu **exibição da fonte de dados** ou clicando com o botão direito do mouse em uma área aberta dos painéis **tabelas** ou **diagrama** .</span><span class="sxs-lookup"><span data-stu-id="849fc-116">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View**  menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
3.  <span data-ttu-id="849fc-117">No painel **Tabelas** ou **Diagrama** , clique com o botão direito do mouse na coluna ou nas colunas que você quer usar para definir uma chave primária lógica e clique em **Definir Chave Primária Lógica**.</span><span class="sxs-lookup"><span data-stu-id="849fc-117">In either the **Tables** or the **Diagram** pane, right-click the column or columns that you want to use to define a logical primary key, and then click **Set Logical Primary Key**.</span></span>  
  
     <span data-ttu-id="849fc-118">A opção para configurar a chave primária lógica estará disponível somente para as tabelas que não possuem uma chave primária.</span><span class="sxs-lookup"><span data-stu-id="849fc-118">The option to set a logical primary key is available only for tables that do not have a primary key.</span></span>  
  
     <span data-ttu-id="849fc-119">Observe que, depois que você define a chave, agora um ícone de chave identifica as colunas de chave primária.</span><span class="sxs-lookup"><span data-stu-id="849fc-119">Notice that after you set the key, a key icon now identifies the primary key columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849fc-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="849fc-120">See Also</span></span>  
 <span data-ttu-id="849fc-121">[Exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="849fc-121">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="849fc-122">Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="849fc-122">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
