---
title: Bancos de dados de desenvolvimento, teste e produção (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- production databases [SQL Server]
- testing databases
- database testing [SQL Server]
ms.assetid: cb403330-8cbe-41c6-bd23-bc432d50f173
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98ac88aec42b53012e0f57233a089bddbd3c8cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679619"
---
# <a name="development-test-and-production-databases-visual-database-tools"></a><span data-ttu-id="97c77-102">Bancos de dados de desenvolvimento, teste e produção (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="97c77-102">Development, Test, and Production Databases (Visual Database Tools)</span></span>
  <span data-ttu-id="97c77-103">Se você tiver dois bancos de dados com estruturas idênticas, poderá fazer alterações em um banco de dados e propagá-las para o outro.</span><span class="sxs-lookup"><span data-stu-id="97c77-103">If you have two databases with identical structure, you can make changes in one database and propagate those changes to the other.</span></span> <span data-ttu-id="97c77-104">Por exemplo, se você tiver um banco de dados de desenvolvimento pessoal e um banco de dados de teste para todo o grupo, poderá modificar o banco de dados de desenvolvimento e depois propagar essas alterações para o banco de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="97c77-104">For example, if you have a personal development database and a group-wide test database, you can modify the development database, then propagate those changes to the test database.</span></span>  
  
 <span data-ttu-id="97c77-105">Para fazer isso, execute todas as modificações em uma única sessão com o banco de dados de desenvolvimento, crie um Script Change de sua sessão e depois execute o script no banco de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="97c77-105">To accomplish this, perform all the modifications in a single session with the development database, create a Change Script of your session and later run the script on the test database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c77-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97c77-106">See Also</span></span>  
 [<span data-ttu-id="97c77-107">Ambientes multiusuários &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="97c77-107">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
