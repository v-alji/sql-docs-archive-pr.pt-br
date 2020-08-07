---
title: Criar a consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682163"
---
# <a name="design-the-query"></a><span data-ttu-id="ccc32-102">Projetar a consulta</span><span class="sxs-lookup"><span data-stu-id="ccc32-102">Design the Query</span></span>
  <span data-ttu-id="ccc32-103">Use esta página do Assistente de Relatório para criar uma consulta, digitando a consulta manualmente, usando o Construtor de Consultas para criar uma consulta interativamente ou importando uma consulta de outro relatório.</span><span class="sxs-lookup"><span data-stu-id="ccc32-103">Use this page of the Report Wizard to create a query by typing the query manually, by using Query Builder to interactively build a query, or by importing a query from another report.</span></span>  
  
 <span data-ttu-id="ccc32-104">O tipo de fonte de dados que você escolheu na página Selecionar a Fonte de Dados, uma página anterior do Assistente de Relatório, determina a consulta que você pode digitar nessa página.</span><span class="sxs-lookup"><span data-stu-id="ccc32-104">The data source type you chose on the Select the Data Source page, a previous page in the Report Wizard, determines the query you can enter on this page.</span></span> <span data-ttu-id="ccc32-105">Por exemplo, se o tipo de fonte de dados for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , você poderá inserir [!INCLUDE[tsql](../includes/tsql-md.md)] instruções ou nomes de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="ccc32-105">For example, if the data source type is [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements or stored procedure names.</span></span> <span data-ttu-id="ccc32-106">Se o tipo de fonte de dados for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , o painel de consulta será desabilitado e você não poderá inserir uma consulta diretamente.</span><span class="sxs-lookup"><span data-stu-id="ccc32-106">If the data source type is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the Query pane is disabled and you cannot enter a query directly.</span></span> <span data-ttu-id="ccc32-107">Você pode especificar a consulta usando o Construtor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="ccc32-107">You can specify the query by using Query Builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ccc32-108">Opções</span><span class="sxs-lookup"><span data-stu-id="ccc32-108">Options</span></span>  
 <span data-ttu-id="ccc32-109">**Cadeia de consulta**</span><span class="sxs-lookup"><span data-stu-id="ccc32-109">**Query string**</span></span>  
 <span data-ttu-id="ccc32-110">Digite uma consulta que recupere os dados que você deseja usar em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="ccc32-110">Type a query that retrieves the data you want to use in your report.</span></span>  
  
 <span data-ttu-id="ccc32-111">**Construtor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="ccc32-111">**Query Builder**</span></span>  
 <span data-ttu-id="ccc32-112">Clique em **Construtor de Consultas** para abrir um designer de consulta para a fonte de dados ou importar uma consulta de outro relatório.</span><span class="sxs-lookup"><span data-stu-id="ccc32-112">Click **Query Builder** to open a query designer for the data source, or to import a query from another report.</span></span>  
  
 <span data-ttu-id="ccc32-113">Para obter mais informações sobre designers de consulta, consulte [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="ccc32-113">For more information about query designers, see [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccc32-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ccc32-114">Example</span></span>  
 <span data-ttu-id="ccc32-115">Para o tipo de fonte de dados **Microsoft SQL Server**, a consulta a seguir recupera uma lista de últimos nomes da tabela de banco de dado [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] `Person` .</span><span class="sxs-lookup"><span data-stu-id="ccc32-115">For the data source type **Microsoft SQL Server**, the following query retrieves a list of last names from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database `Person` table.</span></span>  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 <span data-ttu-id="ccc32-116">Para o tipo de fonte de dados **Microsoft SQL Server**, a consulta a seguir executa o [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] procedimento armazenado `uspGetEmployeeManagers` para o funcionário com identificação número 1:</span><span class="sxs-lookup"><span data-stu-id="ccc32-116">For the data source type **Microsoft SQL Server**, the following query runs the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` for the employee with identification number 1:</span></span>  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccc32-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ccc32-117">See Also</span></span>  
 <span data-ttu-id="ccc32-118">[Ajuda do assistente de relatório](../../2014/reporting-services/report-wizard-help.md) </span><span class="sxs-lookup"><span data-stu-id="ccc32-118">[Report Wizard Help](../../2014/reporting-services/report-wizard-help.md) </span></span>  
 <span data-ttu-id="ccc32-119">[Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ccc32-119">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ccc32-120">Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ccc32-120">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
