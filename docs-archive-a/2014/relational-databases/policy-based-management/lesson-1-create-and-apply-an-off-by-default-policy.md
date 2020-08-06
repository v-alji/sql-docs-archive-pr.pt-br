---
title: 'Lição 1: Criar e aplicar uma política desativada por padrão | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: d31367db-b7db-44c4-8df2-f1240474cf78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a76df1a72b93d09c5c1c199cb0246dbb51c9cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569970"
---
# <a name="lesson-1-create-and-apply-an-off-by-default-policy"></a><span data-ttu-id="2292e-102">Lição 1: Criar e aplicar uma política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="2292e-102">Lesson 1: Create and Apply an Off By Default Policy</span></span>
  <span data-ttu-id="2292e-103">Usando as políticas do Gerenciamento Baseado em Políticas, você pode administrar uma ou mais instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um ou mais objetos de instâncias, instâncias de servidor, bancos de dados ou objetos de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="2292e-103">Using Policy-Based Management policies, you can administer one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], one or more instance objects, server instances, one or more databases, or one or more database objects.</span></span> <span data-ttu-id="2292e-104">Como administrador de banco de dados, você deseja garantir que determinados servidores não tenham o Database Mail habilitado.</span><span class="sxs-lookup"><span data-stu-id="2292e-104">As the database administrator, you want to ensure that certain servers do not have Database Mail enabled.</span></span> <span data-ttu-id="2292e-105">Nesta lição, você criará uma condição e uma política que definirão essa opção de servidor.</span><span class="sxs-lookup"><span data-stu-id="2292e-105">In this lesson, you will create a condition and a policy that sets that server option.</span></span> <span data-ttu-id="2292e-106">Você testará o servidor para ver se ele obedece a política.</span><span class="sxs-lookup"><span data-stu-id="2292e-106">You will test the server to see whether it complies with the policy.</span></span> <span data-ttu-id="2292e-107">Então, você usará a política para reconfigurar o servidor para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2292e-107">Then, you will use the policy to reconfigure the server to bring the server into compliance.</span></span>  
  
 <span data-ttu-id="2292e-108">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="2292e-108">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="2292e-109">Criar a política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="2292e-109">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
-   [<span data-ttu-id="2292e-110">Configurar um servidor para executar a política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="2292e-110">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2292e-111">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="2292e-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2292e-112">Criar a política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="2292e-112">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="2292e-113">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="2292e-113">Next Lesson</span></span>  
 [<span data-ttu-id="2292e-114">Lição 2: Criar e aplicar uma política de nomeação de padrões</span><span class="sxs-lookup"><span data-stu-id="2292e-114">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
