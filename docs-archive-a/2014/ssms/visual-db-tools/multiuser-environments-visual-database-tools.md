---
title: Ambientes multiusuários (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- users [SQL Server], multiuser environments
- conflict resolution [Visual Database Tools]
- multiple users making database changes
- multiuser environments [Visual Database Tools]
- database modifications [SQL Server]
- version control [Visual Database Tools]
- Visual Database Tools [SQL Server], multiuser environments
ms.assetid: 330bd48c-9427-4967-b58e-b7c492d5ee36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2e219ecda25f477aa459de674a43d9c2360376ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571747"
---
# <a name="multiuser-environments-visual-database-tools"></a><span data-ttu-id="dbb6a-102">Ambientes multiusuários (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="dbb6a-102">Multiuser Environments (Visual Database Tools)</span></span>
  <span data-ttu-id="dbb6a-103">Um ambiente multiusuário é um ambiente em que outros usuários podem se conectar e fazer alterações no mesmo banco de dados em que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-103">A multiuser environment is one in which other users can connect and make changes to the same database that you are working with.</span></span> <span data-ttu-id="dbb6a-104">Como resultado, vários usuários podem estar trabalhando ao mesmo tempo com os mesmos objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-104">As a result, several users might be working with the same database objects at the same time.</span></span> <span data-ttu-id="dbb6a-105">Assim, um ambiente multiusuário apresenta a possibilidade de o banco de dados ser afetado por alterações de outros usuários enquanto você faz alterações e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-105">Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.</span></span>  
  
 <span data-ttu-id="dbb6a-106">Um assunto fundamental quando se trabalha com bancos de dados em um ambiente multiusuário diz respeito a permissões de acesso.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-106">A key issue when working with databases in a multiuser environment is access permissions.</span></span> <span data-ttu-id="dbb6a-107">As permissões que você tem para o banco de dados determinam a extensão do trabalho que pode ser realizado no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-107">The permissions you have for the database determine the extent of the work you can do with the database.</span></span> <span data-ttu-id="dbb6a-108">Por exemplo, para fazer alterações em objetos de um banco de dados, você deve ter permissões de gravação adequadas para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-108">For example, to make changes to objects in a database, you must have the appropriate write permissions for the database.</span></span> <span data-ttu-id="dbb6a-109">Para obter mais informações sobre permissões em seu banco de dados, consulte a documentação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-109">For more information about permissions in your database, see your database documentation.</span></span> <span data-ttu-id="dbb6a-110">Para obter mais informações, consulte [Permissões e Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dbb6a-110">For more information see [Permissions and Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="dbb6a-111">Quando você salva alterações em tabelas, o Designer de Tabela verifica se o banco de dados não foi modificado desde a gravação das últimas alterações.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-111">When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes.</span></span> <span data-ttu-id="dbb6a-112">Se outro usuário tiver feito alterações, você será notificado de que o banco de dados foi modificado.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-112">If another user has made changes, you will be notified that the database has been modified.</span></span> <span data-ttu-id="dbb6a-113">Talvez seja necessário reconciliar essas mudanças.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-113">You may need to reconcile these changes.</span></span> <span data-ttu-id="dbb6a-114">Para obter mais informações, veja [Reconciliar alterações feitas por vários usuários &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dbb6a-114">For more information, see [Reconcile Changes Made by Multiple Users &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="dbb6a-115">Em um ambiente multiusuário, algumas considerações especiais devem ser levadas em conta para evitar alterações conflitantes.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-115">In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes.</span></span> <span data-ttu-id="dbb6a-116">Para obter mais informações, consulte [Problemas de evolução do banco de dados &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dbb6a-116">For more information, see [Issues of Database Evolution &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="dbb6a-117">Um modo de evitar problemas é trabalhar em uma cópia do banco de dados, como um banco de dados de teste. Quando você fizer alterações, poderá criar um script para ser executado e fazer as alterações no banco de dados original após a resolução dos conflitos offline.</span><span class="sxs-lookup"><span data-stu-id="dbb6a-117">One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline.</span></span> <span data-ttu-id="dbb6a-118">Para obter mais informações, veja [Bancos de dados de desenvolvimento, teste e produção &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dbb6a-118">For more information see [Development, Test, and Production Databases &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span></span>  
  
  
