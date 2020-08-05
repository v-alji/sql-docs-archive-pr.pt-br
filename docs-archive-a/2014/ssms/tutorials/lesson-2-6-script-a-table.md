---
title: Gerar script de uma tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ea88d736-849e-4368-b55d-06aeee097bf3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 247c839d83768756c57297d47f952401a1c8fd46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572303"
---
# <a name="script-a-table"></a><span data-ttu-id="cdafd-102">Gerar script de uma tabela</span><span class="sxs-lookup"><span data-stu-id="cdafd-102">Script a Table</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="cdafd-103">pode criar scripts para selecionar, inserir, atualizar e excluir tabelas, além de criar, alterar, remover ou executar procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="cdafd-103">can create scripts to select, insert, update, and delete tables, and to create, alter, drop, or execute stored procedures.</span></span>  
  
 <span data-ttu-id="cdafd-104">Às vezes você pode querer um script que tenha várias opções, como remover um procedimento e depois criar um procedimento, ou criar uma tabela e alterá-la.</span><span class="sxs-lookup"><span data-stu-id="cdafd-104">Sometimes you want a script with multiple options, such as drop a procedure and then create a procedure, or create a table then alter a table.</span></span> <span data-ttu-id="cdafd-105">Para criar scripts combinados, salve o primeiro script em uma janela do Editor de Consultas e o segundo na área de transferência para que você possa colá-lo na janela após o primeiro script.</span><span class="sxs-lookup"><span data-stu-id="cdafd-105">To create combined scripts, save the first script to a Query Editor window and the second to the clipboard so you can paste it into the window after the first script.</span></span>  
  
## <a name="creating-an-update-script"></a><span data-ttu-id="cdafd-106">Criando um script de atualização</span><span class="sxs-lookup"><span data-stu-id="cdafd-106">Creating an Update Script</span></span>  
  
#### <a name="to-create-the-insert-script-for-a-table"></a><span data-ttu-id="cdafd-107">Para criar um script de inserção para uma tabela</span><span class="sxs-lookup"><span data-stu-id="cdafd-107">To create the insert script for a table</span></span>  
  
1.  <span data-ttu-id="cdafd-108">No Pesquisador de Objetos, expanda o servidor, expanda **Bancos de Dados**, [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], **Tabelas**, clique com o botão direito do mouse em **HumanResources.Employee**e aponte para **Criar Script de Tabela Como**.</span><span class="sxs-lookup"><span data-stu-id="cdafd-108">In Object Explorer, expand your server, expand **Databases**, expand [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], expand **Tables**, right-click **HumanResources.Employee**, and then point to **Script Table As**.</span></span>  
  
2.  <span data-ttu-id="cdafd-109">O menu de atalho tem sete opções de script disponíveis: **CREATE To**, **DROP To**, **DROP e CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**e **DELETE To**.</span><span class="sxs-lookup"><span data-stu-id="cdafd-109">The shortcut menu has seven available scripting options: **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**, and **DELETE To**.</span></span> <span data-ttu-id="cdafd-110">Aponte para **UPDATE To**e clique em **Nova Janela do Editor de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="cdafd-110">Point to **UPDATE To**, and then click **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="cdafd-111">Uma nova janela do Editor de Consultas é aberta, estabelece uma conexão e apresenta a instrução de atualização inteira.</span><span class="sxs-lookup"><span data-stu-id="cdafd-111">A new Query Editor window opens, makes a connection, and presents the entire update statement.</span></span>  
  
     <span data-ttu-id="cdafd-112">Esse exercício demonstra como o recurso de script pode fazer mais do que simplesmente executar o script de criação de uma tabela ou procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="cdafd-112">This exercise demonstrates how the scripting feature can do more than just script the creation of a table or stored procedure.</span></span> <span data-ttu-id="cdafd-113">Esse novo recurso pode ajudá-lo a adicionar rapidamente scripts de manipulação de dados a seu projeto e a executar scripts de procedimento armazenados com facilidade.</span><span class="sxs-lookup"><span data-stu-id="cdafd-113">This new feature can help you quickly add data manipulation scripts to your project and easily script execution of stored procedures.</span></span> <span data-ttu-id="cdafd-114">Isso pode economizar tempo em tabelas e procedimentos com muitos campos.</span><span class="sxs-lookup"><span data-stu-id="cdafd-114">This can be a big timesaver for tables and procedures with many fields.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cdafd-115">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="cdafd-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cdafd-116">Resumo: Gravando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cdafd-116">Summary: Writing Transact-SQL</span></span>](../../tutorials/summary-writing-transact-sql.md)  
  
  
