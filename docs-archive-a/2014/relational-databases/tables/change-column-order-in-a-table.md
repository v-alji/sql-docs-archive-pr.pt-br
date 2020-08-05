---
title: Alterar a ordem das colunas em uma tabela| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
author: stevestein
ms.author: sstein
ms.openlocfilehash: d162f9dc793ceb9ea423d94922f7358f1729712e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573885"
---
# <a name="change-column-order-in-a-table"></a><span data-ttu-id="712cb-102">Alterar ordem de colunas em uma tabela</span><span class="sxs-lookup"><span data-stu-id="712cb-102">Change Column Order in a Table</span></span>
  <span data-ttu-id="712cb-103">Você pode alterar a ordem das colunas no Designer de Tabela do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="712cb-103">You can change the order of columns in Table Designer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="712cb-104">A alteração da ordem das colunas de uma tabela pode afetar o código e os aplicativos que dependam da ordem específica das colunas.</span><span class="sxs-lookup"><span data-stu-id="712cb-104">Changing the column order of a table may affect code and applications that depend on the specific order of columns.</span></span> <span data-ttu-id="712cb-105">Isso inclui consultas, exibições, procedimentos armazenados, funções definidas pelo usuário e aplicativos clientes.</span><span class="sxs-lookup"><span data-stu-id="712cb-105">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="712cb-106">Analise cuidadosamente todas as alterações que deseja fazer à ordem das colunas antes fazê-las.</span><span class="sxs-lookup"><span data-stu-id="712cb-106">Carefully consider any changes you want to make to column order before making it.</span></span> <span data-ttu-id="712cb-107">A prática recomendada é especificar a ordem em que as colunas serão retornadas nos níveis de aplicativo e de consulta.</span><span class="sxs-lookup"><span data-stu-id="712cb-107">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="712cb-108">Você não deve confiar no uso de SELECT \* para retornar todas as colunas na ordem esperada com base na ordem em que são definidas na tabela.</span><span class="sxs-lookup"><span data-stu-id="712cb-108">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="712cb-109">Sempre especifique as colunas por nome em suas consultas e aplicativos na ordem em que você gostaria que elas aparecessem.</span><span class="sxs-lookup"><span data-stu-id="712cb-109">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
 <span data-ttu-id="712cb-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="712cb-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="712cb-111">**Para alterar a ordem das colunas usando:**</span><span class="sxs-lookup"><span data-stu-id="712cb-111">**To change the column order, using:**</span></span>  
  
     [<span data-ttu-id="712cb-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="712cb-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="712cb-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="712cb-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="712cb-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="712cb-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-column-order"></a><span data-ttu-id="712cb-115">Para alterar a ordem das colunas</span><span class="sxs-lookup"><span data-stu-id="712cb-115">To change the column order</span></span>  
  
1.  <span data-ttu-id="712cb-116">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela cujas colunas você deseja reordenar e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="712cb-116">In **Object Explorer**, right-click the table with columns you want to reorder and click **Design**.</span></span>  
  
2.  <span data-ttu-id="712cb-117">Selecione a caixa à esquerda do nome da coluna que você deseja reordenar.</span><span class="sxs-lookup"><span data-stu-id="712cb-117">Select the box to the left of the column name that you want to reorder.</span></span>  
  
3.  <span data-ttu-id="712cb-118">Arraste a coluna para outro local dentro da tabela.</span><span class="sxs-lookup"><span data-stu-id="712cb-118">Drag the column to another location within the table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="712cb-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="712cb-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="712cb-120">**Para alterar a ordem das colunas**</span><span class="sxs-lookup"><span data-stu-id="712cb-120">**To change the column order**</span></span>  
  
 <span data-ttu-id="712cb-121">Esta tarefa não pode ser executada usando instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="712cb-121">This task cannot be performed using Transact-SQL statements.</span></span>  
  
###  <a name="TsqlExample"></a>  
