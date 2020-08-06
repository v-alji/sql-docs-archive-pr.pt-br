---
title: Executar arquivos de script Transact-SQL usando sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
author: rothja
ms.author: jroth
ms.openlocfilehash: cd34b089fc4e971cac9e5713cbe303192a7a48c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570590"
---
# <a name="run-transact-sql-script-files-using-sqlcmd"></a><span data-ttu-id="9baff-102">Executar arquivos de script Transact-SQL usando sqlcmd</span><span class="sxs-lookup"><span data-stu-id="9baff-102">Run Transact-SQL Script Files Using sqlcmd</span></span>
  <span data-ttu-id="9baff-103">Você pode usar `sqlcmd` para executar um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9baff-103">You can use `sqlcmd` to run a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="9baff-104">Um arquivo de script do [!INCLUDE[tsql](../../includes/tsql-md.md)] é um arquivo de texto que contém uma combinação de instruções do [!INCLUDE[tsql](../../includes/tsql-md.md)], comandos e variáveis de script do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="9baff-104">A [!INCLUDE[tsql](../../includes/tsql-md.md)] script file is a text file that can contain a combination of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="9baff-105">Para criar um arquivo simples de script do [!INCLUDE[tsql](../../includes/tsql-md.md)] usando o Bloco de Notas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9baff-105">To create a simple [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using Notepad, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9baff-106">Clique em **Iniciar**, selecione **Todos os Programas**, vá até **Acessórios**e, depois, clique em **Bloco de Notas**.</span><span class="sxs-lookup"><span data-stu-id="9baff-106">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad**.</span></span>  
  
2.  <span data-ttu-id="9baff-107">Copie e cole o seguinte código do [!INCLUDE[tsql](../../includes/tsql-md.md)] no Bloco de Notas:</span><span class="sxs-lookup"><span data-stu-id="9baff-107">Copy and paste the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code into Notepad:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  <span data-ttu-id="9baff-108">Salve o arquivo como **myScript.sql** na unidade C.</span><span class="sxs-lookup"><span data-stu-id="9baff-108">Save the file as **myScript.sql** in the C drive.</span></span>  
  
### <a name="to-run-the-script-file"></a><span data-ttu-id="9baff-109">Para executar o arquivo de script</span><span class="sxs-lookup"><span data-stu-id="9baff-109">To run the script file</span></span>  
  
1.  <span data-ttu-id="9baff-110">Abra uma janela de prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9baff-110">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="9baff-111">Na janela do prompt de comando, digite: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span><span class="sxs-lookup"><span data-stu-id="9baff-111">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span></span>  
  
3.  <span data-ttu-id="9baff-112">Pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="9baff-112">Press ENTER.</span></span>  
  
 <span data-ttu-id="9baff-113">Uma lista de nomes e endereços de funcionários do [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] é escrita na janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9baff-113">A list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] employee names and addresses is written to the command prompt window.</span></span>  
  
### <a name="to-save-this-output-to-a-text-file"></a><span data-ttu-id="9baff-114">Para salvar essa saída em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="9baff-114">To save this output to a text file</span></span>  
  
1.  <span data-ttu-id="9baff-115">Abra uma janela de prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9baff-115">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="9baff-116">Na janela do prompt de comando, digite: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span><span class="sxs-lookup"><span data-stu-id="9baff-116">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span></span>  
  
3.  <span data-ttu-id="9baff-117">Pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="9baff-117">Press ENTER.</span></span>  
  
 <span data-ttu-id="9baff-118">Nenhuma saída é retornada na janela de prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9baff-118">No output is returned in the Command Prompt window.</span></span> <span data-ttu-id="9baff-119">Em vez disso, a saída é enviada ao arquivo EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="9baff-119">Instead, the output is sent to the EmpAdds.txt file.</span></span> <span data-ttu-id="9baff-120">Você pode verificar essa saída abrindo o arquivo EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="9baff-120">You can verify this output by opening the EmpAdds.txt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9baff-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9baff-121">See Also</span></span>  
 <span data-ttu-id="9baff-122">[Iniciar o utilitário sqlcmd](sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9baff-122">[Start the sqlcmd Utility](sqlcmd-start-the-utility.md) </span></span>  
 [<span data-ttu-id="9baff-123">Utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="9baff-123">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
