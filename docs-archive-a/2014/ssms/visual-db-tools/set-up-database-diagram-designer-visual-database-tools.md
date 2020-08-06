---
title: Configurar o Designer de Diagramas de Banco de Dados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.InstallSqlDiagramSupport
helpviewer_keywords:
- Database Diagram Designer
- database diagrams [SQL Server], Database Diagram Designer
- diagrams [SQL Server], Database Diagram Designer
ms.assetid: 927321ee-b459-4f5b-9719-4a7a95639143
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d59fa2ed197a410de6b68e388e76d2bf21c334d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682039"
---
# <a name="set-up-database-diagram-designer-visual-database-tools"></a><span data-ttu-id="66e53-102">Configurar o Designer de Diagramas de Banco de Dados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="66e53-102">Set Up Database Diagram Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="66e53-103">Para usar o Designer de Diagramas de Banco de Dados, ele precisa ser configurado primeiramente por um membro da função **db_owner** para controlar o acesso a diagramas.</span><span class="sxs-lookup"><span data-stu-id="66e53-103">To use Database Diagram Designer, it must first be set up by a member of the **db_owner** role to control access to diagrams.</span></span>  
  
### <a name="to-set-up-database-diagramming"></a><span data-ttu-id="66e53-104">Para configurar a diagramação de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="66e53-104">To set up database diagramming</span></span>  
  
1.  <span data-ttu-id="66e53-105">Utilizando o Pesquisador de Objetos, expanda um nó do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="66e53-105">From Object Explorer, expand a database node.</span></span>  
  
2.  <span data-ttu-id="66e53-106">Expanda o nó Diagrama de Banco de Dados na conexão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="66e53-106">Expand the Database Diagrams node under the database connection.</span></span>  
  
3.  <span data-ttu-id="66e53-107">Selecione **Sim** quando solicitado se desejar configurar a diagramação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="66e53-107">Select **Yes** when prompted if you want to set up database diagramming.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66e53-108">Isso criará a tabela de diagrama de banco de dados, os procedimentos armazenados do sistema e uma função do sistema no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66e53-108">This will create the database diagram table, system stored procedures, and a system function on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="66e53-109">O Visual Studio criará os seguintes objetos na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="66e53-109">Visual Studio will create the following objects on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="66e53-110">Tabela sysdiagrams</span><span class="sxs-lookup"><span data-stu-id="66e53-110">sysdiagrams table</span></span>  
  
    2.  <span data-ttu-id="66e53-111">Procedimento armazenado sp_alterdiagram</span><span class="sxs-lookup"><span data-stu-id="66e53-111">sp_alterdiagram stored procedure</span></span>  
  
    3.  <span data-ttu-id="66e53-112">Procedimento armazenado sp_creatediagram</span><span class="sxs-lookup"><span data-stu-id="66e53-112">sp_creatediagram stored procedure</span></span>  
  
    4.  <span data-ttu-id="66e53-113">Procedimento armazenado sp_dropdiagram</span><span class="sxs-lookup"><span data-stu-id="66e53-113">sp_dropdiagram stored procedure</span></span>  
  
    5.  <span data-ttu-id="66e53-114">Procedimento armazenado sp_renamediagram</span><span class="sxs-lookup"><span data-stu-id="66e53-114">sp_renamediagram stored procedure</span></span>  
  
    6.  <span data-ttu-id="66e53-115">Função fn_diagramobjects</span><span class="sxs-lookup"><span data-stu-id="66e53-115">fn_diagramobjects function</span></span>  
  
    7.  <span data-ttu-id="66e53-116">Procedimento armazenado sp_helpdiagrams</span><span class="sxs-lookup"><span data-stu-id="66e53-116">sp_helpdiagrams stored procedure</span></span>  
  
    8.  <span data-ttu-id="66e53-117">Procedimento armazenado sp_helpdiagramsdefinition</span><span class="sxs-lookup"><span data-stu-id="66e53-117">sp_helpdiagramsdefinition stored procedure</span></span>  
  
    9. <span data-ttu-id="66e53-118">Procedimento armazenado sp_upgraddiagrams</span><span class="sxs-lookup"><span data-stu-id="66e53-118">sp_upgraddiagrams stored procedure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e53-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66e53-119">See Also</span></span>  
 <span data-ttu-id="66e53-120">[Entender a propriedade do diagrama de banco de dados &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="66e53-120">[Understand Database Diagram Ownership &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="66e53-121">[Atualizar diagramas de banco de dados de edições anteriores &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="66e53-121">[Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="66e53-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="66e53-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
  
