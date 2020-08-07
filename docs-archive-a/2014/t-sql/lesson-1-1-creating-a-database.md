---
title: Criando um banco de dados (tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 99d5439c289b5d4e71786d4c6734f158f6bba371
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575486"
---
# <a name="creating-a-database-tutorial"></a><span data-ttu-id="47384-102">Criando um banco de dados (tutorial)</span><span class="sxs-lookup"><span data-stu-id="47384-102">Creating a Database (Tutorial)</span></span>
  <span data-ttu-id="47384-103">Como muitas instruções [!INCLUDE[tsql](../includes/tsql-md.md)] , a instrução CREATE DATABASE tem um parâmetro obrigatório: o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47384-103">Like many [!INCLUDE[tsql](../includes/tsql-md.md)] statements, the CREATE DATABASE statement has a required parameter: the name of the database.</span></span> <span data-ttu-id="47384-104">CREATE DATABASE também tem muitos parâmetros opcionais, como o local de disco onde você deseja armazenar os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47384-104">CREATE DATABASE also has many optional parameters, such as the disk location where you want to put the database files.</span></span> <span data-ttu-id="47384-105">Quando você executa CREATE DATABASE sem os parâmetros opcionais, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa valores padrão para muitos destes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="47384-105">When you execute CREATE DATABASE without the optional parameters, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses default values for many of these parameters.</span></span> <span data-ttu-id="47384-106">Este tutorial usa poucos parâmetros de sintaxe opcionais.</span><span class="sxs-lookup"><span data-stu-id="47384-106">This tutorial uses very few of the optional syntax parameters.</span></span>  
  
### <a name="to-create-a-database"></a><span data-ttu-id="47384-107">Para criar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="47384-107">To create a database</span></span>  
  
1.  <span data-ttu-id="47384-108">Em uma janela do Editor de Consultas, digite, mas não execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="47384-108">In a Query Editor window, type but do not execute the following code:</span></span>  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  <span data-ttu-id="47384-109">Use o ponteiro para selecionar as palavras `CREATE DATABASE`e, em seguida, pressione **F1**.</span><span class="sxs-lookup"><span data-stu-id="47384-109">Use the pointer to select the words `CREATE DATABASE`, and then press **F1**.</span></span> <span data-ttu-id="47384-110">O tópico CREATE DATABASE será exibido em Manuais Online do SQL.</span><span class="sxs-lookup"><span data-stu-id="47384-110">The CREATE DATABASE topic in SQL Server Books Online should open.</span></span> <span data-ttu-id="47384-111">Você pode usar esta técnica para localizar a sintaxe completa de CREATE DATABASE e para as outras instruções que são usadas neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="47384-111">You can use this technique to find the complete syntax for CREATE DATABASE and for the other statements that are used in this tutorial.</span></span>  
  
3.  <span data-ttu-id="47384-112">No Editor de Consultas, pressione **F5** para executar a instrução e criar um banco de dados denominado `TestData`.</span><span class="sxs-lookup"><span data-stu-id="47384-112">In Query Editor, press **F5** to execute the statement and create a database named `TestData`.</span></span>  
  
 <span data-ttu-id="47384-113">Ao criar um banco de dados, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] faz uma cópia do banco de dados **modelo** e renomeia a cópia para o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47384-113">When you create a database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] makes a copy of the **model** database, and renames the copy to the database name.</span></span> <span data-ttu-id="47384-114">Esta operação deve levar somente alguns segundos, a menos que você especifique um tamanho inicial grande do banco de dados como um parâmetro opcional.</span><span class="sxs-lookup"><span data-stu-id="47384-114">This operation should only take several seconds, unless you specify a large initial size of the database as an optional parameter.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47384-115">A palavra-chave GO separa instruções quando mais de uma instrução é enviada em um único lote.</span><span class="sxs-lookup"><span data-stu-id="47384-115">The keyword GO separates statements when more than one statement is submitted in a single batch.</span></span> <span data-ttu-id="47384-116">GO é opcional quando o lote contém somente uma instrução.</span><span class="sxs-lookup"><span data-stu-id="47384-116">GO is optional when the batch contains only one statement.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="47384-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="47384-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="47384-118">Criando uma tabela &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="47384-118">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="47384-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47384-119">See Also</span></span>  
 [<span data-ttu-id="47384-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47384-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
