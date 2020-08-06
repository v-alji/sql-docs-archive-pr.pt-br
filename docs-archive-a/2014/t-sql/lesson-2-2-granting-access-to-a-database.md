---
title: Concedendo acesso a um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582726"
---
# <a name="granting-access-to-a-database"></a><span data-ttu-id="b4c8e-102">concedendo acesso a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b4c8e-102">Granting Access to a Database</span></span>
  <span data-ttu-id="b4c8e-103">Mary agora tem acesso a esta instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mas não tem permissão para acessar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="b4c8e-103">Mary now has access to this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but does not have permission to access the databases.</span></span> <span data-ttu-id="b4c8e-104">Ela não tem acesso nem mesmo ao seu banco de dados padrão **TestData** até que você a autorize como usuária de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4c8e-104">She does not even have access to her default database **TestData** until you authorize her as a database user.</span></span>  
  
 <span data-ttu-id="b4c8e-105">Para conceder acesso à Mary, alterne para o banco de dados **TestData** e, em seguida, use a instrução CREATE USER para mapear o logon dela para um usuário nomeado Mary.</span><span class="sxs-lookup"><span data-stu-id="b4c8e-105">To grant Mary access, switch to the **TestData** database, and then use the CREATE USER statement to map her login to a user named Mary.</span></span>  
  
### <a name="to-create-a-user-in-a-database"></a><span data-ttu-id="b4c8e-106">Para criar um usuário em um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b4c8e-106">To create a user in a database</span></span>  
  
1.  <span data-ttu-id="b4c8e-107">Digite e execute as instruções a seguir (substituindo `computer_name` pelo nome de seu computador) para conceder acesso à `Mary` ao banco de dados `TestData` .</span><span class="sxs-lookup"><span data-stu-id="b4c8e-107">Type and execute the following statements (replacing `computer_name` with the name of your computer) to grant `Mary` access to the `TestData` database.</span></span>  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     <span data-ttu-id="b4c8e-108">Agora, Mary tem acesso ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e ao banco de dados `TestData` .</span><span class="sxs-lookup"><span data-stu-id="b4c8e-108">Now, Mary has access to both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the `TestData` database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b4c8e-109">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="b4c8e-109">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b4c8e-110">Criando exibições e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="b4c8e-110">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
