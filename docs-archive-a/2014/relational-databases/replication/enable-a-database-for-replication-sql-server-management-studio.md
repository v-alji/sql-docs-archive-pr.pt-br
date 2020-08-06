---
title: Habilitar um banco de dados para replicação (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569912"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a><span data-ttu-id="faed8-102">Habilitar um banco de dados para replicação (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="faed8-102">Enable a Database for Replication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="faed8-103">Um banco de dados está implicitamente habilitado para replicação quando um membro da função do servidor fixa **sysadmin** cria uma publicação no Assistente para Novas Publicações.</span><span class="sxs-lookup"><span data-stu-id="faed8-103">A database is implicitly enabled for replication when a member of the **sysadmin** fixed server role creates a publication with the New Publication Wizard.</span></span> <span data-ttu-id="faed8-104">Um membro da função de servidor fixa **sysadmin** também pode habilitar um banco de dados explicitamente para replicação, assim, um membro da função de banco de dados fixa **db_owner** pode criar uma ou mais publicações naquele banco de dados.</span><span class="sxs-lookup"><span data-stu-id="faed8-104">A member of the **sysadmin** fixed server role can also enable a database for replication explicitly, so that a member of the **db_owner** fixed database role can create one or more publications in that database.</span></span> <span data-ttu-id="faed8-105">Para habilitar um banco de dados explicitamente, use a página **Bancos de Dados de Publicação** da caixa de diálogo **Propriedades do Editor – \<Publisher>** .</span><span class="sxs-lookup"><span data-stu-id="faed8-105">To enable a database explicitly, use the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box.</span></span> <span data-ttu-id="faed8-106">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="faed8-106">For more information about accessing this dialog box, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
### <a name="to-enable-a-database-for-replication"></a><span data-ttu-id="faed8-107">Para habilitar um banco de dados para replicação</span><span class="sxs-lookup"><span data-stu-id="faed8-107">To enable a database for replication</span></span>  
  
1.  <span data-ttu-id="faed8-108">Na página **Bancos de Dados de Publicação** da caixa de diálogo **Propriedades do Editor – \<Publisher>** , selecione a caixa de seleção **Transacional** e/ou **Mesclagem** para cada banco de dados que deseja replicar.</span><span class="sxs-lookup"><span data-stu-id="faed8-108">On the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box, select the **Transactional** and/or **Merge** check box for each database you want to replicate.</span></span> <span data-ttu-id="faed8-109">Selecione **Transacional** para habilitar o banco de dados para replicação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="faed8-109">Select **Transactional** to enable the database for snapshot replication.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
