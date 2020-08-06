---
title: Opções (resultados da consulta-SQL Server-multi-Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8273ad5edc65dd7351533209e9fa670c49f75f7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683669"
---
# <a name="options-query-results-sql-server-multi-server"></a><span data-ttu-id="42564-102">Opções (Resultados da Consulta/SQL Server/Multisservidor)</span><span class="sxs-lookup"><span data-stu-id="42564-102">Options (Query Results-SQL Server-Multi-Server)</span></span>
  <span data-ttu-id="42564-103">Ao consultar vários servidores ao mesmo tempo, use esta página para especificar as opções de exibição de um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="42564-103">When you are querying multiple servers at the same time, use this page to specify the options for displaying result sets.</span></span> <span data-ttu-id="42564-104">A mesclagem de resultados combina os conjuntos de resultados de todos os servidores em um único conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="42564-104">Merge results combines the result sets from all servers into a single result set.</span></span> <span data-ttu-id="42564-105">Ao mesclar resultados, o primeiro servidor que responde define o esquema para o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="42564-105">When merging results, the first server to respond sets the schema for the result set.</span></span> <span data-ttu-id="42564-106">Para mesclar os conjuntos de resultados, a consulta deve retornar o mesmo número de colunas, com os mesmos nomes de colunas de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="42564-106">To merge the result sets, the query must return the same number of columns with the same column names from each server.</span></span> <span data-ttu-id="42564-107">Ao mesclar resultados, uma mensagem é exibida para cada servidor que não corresponde ao esquema (contagem e nomes de colunas) que é retornado pelo primeiro servidor que retorna resultados.</span><span class="sxs-lookup"><span data-stu-id="42564-107">When merging results, a message is displayed for each server that does not match the schema (column count and column names) that is returned by the first server to return results.</span></span>  
  
 <span data-ttu-id="42564-108">Se você não mesclar resultados, o conjunto de resultados de cada servidor será exibido em sua própria grade com seu próprio esquema.</span><span class="sxs-lookup"><span data-stu-id="42564-108">When you do not merge results, the result set from each server will be displayed in its own grid with its own schema.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="42564-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="42564-109">UI element list</span></span>  
 <span data-ttu-id="42564-110">**Mesclar resultados**</span><span class="sxs-lookup"><span data-stu-id="42564-110">**Merge results**</span></span>  
 <span data-ttu-id="42564-111">Selecione esta caixa de seleção para combinar os conjuntos de resultados de vários servidores na mesma grade.</span><span class="sxs-lookup"><span data-stu-id="42564-111">Select this check box to combine the result sets from several servers into the same grid.</span></span>  
  
 <span data-ttu-id="42564-112">**Adicionar nome do servidor aos resultados**</span><span class="sxs-lookup"><span data-stu-id="42564-112">**Add server name to the results**</span></span>  
 <span data-ttu-id="42564-113">Selecione esta caixa de seleção para incluir uma coluna adicional que indica o nome do servidor que gerou cada linha.</span><span class="sxs-lookup"><span data-stu-id="42564-113">Select this check box to include an additional column that provides the name of the server that produced each row.</span></span>  
  
 <span data-ttu-id="42564-114">**Adicionar nome de logon aos resultados**</span><span class="sxs-lookup"><span data-stu-id="42564-114">**Add login name to the results**</span></span>  
 <span data-ttu-id="42564-115">Selecione esta caixa de seleção para incluir uma coluna adicional que indica o logon usado para conectar-se ao servidor que gerou cada linha.</span><span class="sxs-lookup"><span data-stu-id="42564-115">Select this check box to include an additional column that provides the login that was used to connect to the server that provided each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42564-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42564-116">See Also</span></span>  
 <span data-ttu-id="42564-117">[Criar um servidor de gerenciamento central e um grupo de servidores &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span><span class="sxs-lookup"><span data-stu-id="42564-117">[Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span></span>  
 [<span data-ttu-id="42564-118">Executar instruções em vários servidores simultaneamente &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="42564-118">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
