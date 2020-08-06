---
title: 'Lição 2: Configurando permissões em objetos de banco de dados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- database permissions
ms.assetid: f964b66a-ec32-44c2-a185-6a0f173bfa22
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fcc6ee3ddf9be072b51bd568fd3e72eb6c871785
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684972"
---
# <a name="lesson-2-configuring-permissions-on-database-objects"></a><span data-ttu-id="5cd7e-102">Lição 2: Configurando permissões em objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="5cd7e-102">Lesson 2: Configuring Permissions on Database Objects</span></span>
  <span data-ttu-id="5cd7e-103">Conceder um acesso de usuário a um banco de dados envolve três etapas.</span><span class="sxs-lookup"><span data-stu-id="5cd7e-103">Granting a user access to a database involves three steps.</span></span> <span data-ttu-id="5cd7e-104">Primeiro, crie um logon.</span><span class="sxs-lookup"><span data-stu-id="5cd7e-104">First, you create a login.</span></span> <span data-ttu-id="5cd7e-105">O logon permite que o usuário se conecte ao [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cd7e-105">The login lets the user connect to the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="5cd7e-106">Em seguida, configure o logon como um usuário no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="5cd7e-106">Then you configure the login as a user in the specified database.</span></span> <span data-ttu-id="5cd7e-107">E, finalmente, conceda essa permissão de usuário a objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5cd7e-107">And finally, you grant that user permission to database objects.</span></span> <span data-ttu-id="5cd7e-108">Esta lição mostra essas três etapas e demonstra como criar uma exibição e um procedimento armazenado como o objeto.</span><span class="sxs-lookup"><span data-stu-id="5cd7e-108">This lesson shows you these three steps, and shows you how to create a view and a stored procedure as the object.</span></span>  
  
 <span data-ttu-id="5cd7e-109">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="5cd7e-109">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="5cd7e-110">criando um logon</span><span class="sxs-lookup"><span data-stu-id="5cd7e-110">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
-   [<span data-ttu-id="5cd7e-111">concedendo acesso a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="5cd7e-111">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
-   [<span data-ttu-id="5cd7e-112">Criando exibições e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="5cd7e-112">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
-   [<span data-ttu-id="5cd7e-113">concedendo acesso a um objeto de banco de dados</span><span class="sxs-lookup"><span data-stu-id="5cd7e-113">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
-   [<span data-ttu-id="5cd7e-114">resumo: configurando permissões em objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="5cd7e-114">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5cd7e-115">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="5cd7e-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5cd7e-116">criando um logon</span><span class="sxs-lookup"><span data-stu-id="5cd7e-116">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
  
