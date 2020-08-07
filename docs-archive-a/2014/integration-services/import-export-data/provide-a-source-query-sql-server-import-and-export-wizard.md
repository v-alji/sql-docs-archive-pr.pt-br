---
title: Fornecer uma consulta de origem (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.providesourcequery.f1
ms.assetid: c8cbd07e-b9c3-422f-94b8-d6fc8cf31cf5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b21100f51c279e9ba764c8f82565af9d6e391ef3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575928"
---
# <a name="provide-a-source-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="a557a-102">Fornecer uma consulta de origem (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a557a-102">Provide a Source Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="a557a-103">Use a página **fornecer uma consulta de origem** para digitar a instrução SQL que irá gerar os dados a serem copiados da fonte de dados para o destino.</span><span class="sxs-lookup"><span data-stu-id="a557a-103">Use the **Provide a Source Query** page to type the SQL statement that will generate the data to copy from the data source to the destination.</span></span>  
  
 <span data-ttu-id="a557a-104">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a557a-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="a557a-105">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a557a-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="a557a-106">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="a557a-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="a557a-107">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="a557a-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="a557a-108">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="a557a-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="a557a-109">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a557a-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a557a-110">Opções</span><span class="sxs-lookup"><span data-stu-id="a557a-110">Options</span></span>  
 <span data-ttu-id="a557a-111">**Instrução SQL**</span><span class="sxs-lookup"><span data-stu-id="a557a-111">**SQL statement**</span></span>  
 <span data-ttu-id="a557a-112">Digite uma instrução de consulta para recuperar linhas selecionadas de dados do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="a557a-112">Type a query statement to retrieve selected rows of data from the source database.</span></span> <span data-ttu-id="a557a-113">Por exemplo, a instrução de consulta a seguir recupera **vendedorid**, **SalesQuota**e **SalesYTD** do banco de dados AdventureWorks para pessoas de vendas cujo percentual de Comissão é maior que 1,5%.</span><span class="sxs-lookup"><span data-stu-id="a557a-113">For example, the following query statement retrieves the **SalesPersonID**, **SalesQuota**, and **SalesYTD** from the AdventureWorks database for sales persons whose commission percentage is more than 1.5 percent.</span></span>  
  
```  
SELECT SalesPersonID, SalesQuota, SalesYTD  
FROM Sales.SalesPerson  
WHERE CommissionPct > 0.015  
```  
  
 <span data-ttu-id="a557a-114">**Analisar**</span><span class="sxs-lookup"><span data-stu-id="a557a-114">**Parse**</span></span>  
 <span data-ttu-id="a557a-115">Verifica a sintaxe da instrução SQL na caixa de texto **Instrução SQL**.</span><span class="sxs-lookup"><span data-stu-id="a557a-115">Checks the syntax of the SQL statement in the **SQL statement** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a557a-116">Se o tempo necessário para verificar a sintaxe da instrução ultrapassar o valor de tempo limite, que é de 30 segundos, a análise será interrompida e será gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="a557a-116">If the time that is required to check the syntax of the statement exceeds the time-out value of 30 seconds, parsing stops and generates an error.</span></span> <span data-ttu-id="a557a-117">Você só conseguirá ir além dessa página do assistente quando a análise for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="a557a-117">You will not be able to move past this page of the wizard until parsing succeeds.</span></span> <span data-ttu-id="a557a-118">Uma solução possível é criar uma exibição de banco de dados com base na consulta e consultar a exibição usando o assistente em vez de inserir o texto da consulta diretamente.</span><span class="sxs-lookup"><span data-stu-id="a557a-118">One solution is to create a database view based on the query, and to query the view from the wizard, instead of entering the query text directly.</span></span>  
  
 <span data-ttu-id="a557a-119">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="a557a-119">**Browse**</span></span>  
 <span data-ttu-id="a557a-120">Selecione um arquivo que contém uma instrução SQL usando a caixa de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="a557a-120">Select a file containing a SQL statement by using the **Open** dialog box.</span></span> <span data-ttu-id="a557a-121">A seleção de um arquivo copia o texto do arquivo para a caixa de texto **instrução de consulta** .</span><span class="sxs-lookup"><span data-stu-id="a557a-121">Selecting a file copies the text from the file into the **Query statement** text box.</span></span>  
  
  
