---
title: Verificar se nenhum arquivo de banco de dados está em unidades compactadas durante o processo de atualização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- compressed drives [SQL Server]
ms.assetid: 63be6853-c54a-42b2-ae1a-db2175f1d28e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9c04f7890ba8d8efe64afaf11b922af156c5de46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569821"
---
# <a name="verify-that-no-database-files-are-on-compressed-drives-during-the-upgrade-process"></a><span data-ttu-id="a2af8-102">Verificar se não há arquivos de banco de dados em unidades compactadas durante o processo de atualização</span><span class="sxs-lookup"><span data-stu-id="a2af8-102">Verify that no database files are on compressed drives during the upgrade process</span></span>
  <span data-ttu-id="a2af8-103">O Supervisor de Atualização detectou arquivos de banco de dados em uma unidade compactada.</span><span class="sxs-lookup"><span data-stu-id="a2af8-103">Upgrade Advisor detected database files on a compressed drive.</span></span> <span data-ttu-id="a2af8-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode criar nem atualizar bancos de dados em unidades compactadas.</span><span class="sxs-lookup"><span data-stu-id="a2af8-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot create or upgrade databases on compressed drives.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a2af8-105">Componente</span><span class="sxs-lookup"><span data-stu-id="a2af8-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="a2af8-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="a2af8-106">Corrective Action</span></span>  
 <span data-ttu-id="a2af8-107">Ao instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], selecione uma unidade não compactada para os bancos de dados do sistema e certifique-se de que os bancos de dados que serão atualizados não estão em unidades compactadas.</span><span class="sxs-lookup"><span data-stu-id="a2af8-107">When you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select an uncompressed drive for system databases and verify that databases to be upgraded are not on compressed drives.</span></span> <span data-ttu-id="a2af8-108">Porém, saiba que depois que o banco de dados foi atualizado, você pode colocar bancos de dados somente leitura e grupos de arquivos secundários somente leitura em um sistema de arquivo compactado NTFS.</span><span class="sxs-lookup"><span data-stu-id="a2af8-108">However, note that after the database has been upgraded, you can put read-only databases and read-only secondary filegroups on an NTFS compressed file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2af8-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2af8-109">See Also</span></span>  
 <span data-ttu-id="a2af8-110">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a2af8-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a2af8-111">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="a2af8-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
