---
title: Use o caminho completo para registrar nomes de DLL de procedimento armazenado estendido | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- registering DLL names
- extended stored procedures [SQL Server], registering
- DLL names [SQL Server]
- full path DLL name registration [SQL Server]
ms.assetid: f648d57c-af32-4c71-9882-47b6766f3c2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5ec4ef3fc2e0f2c4834ffa7479a00562ae15d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680747"
---
# <a name="use-the-full-path-to-register-extended-stored-procedure-dll-names"></a><span data-ttu-id="c8541-102">Usar caminho completo para registrar nomes de DLL de procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="c8541-102">Use the full path to register extended stored procedure DLL names</span></span>
  <span data-ttu-id="c8541-103">Procedimentos armazenados estendidos que foram registrados anteriormente sem um caminho completo para o nome de DLL podem não funcionar no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8541-103">Extended stored procedures that were previously registered without the full path for the DLL name may not work in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="c8541-104">Componente</span><span class="sxs-lookup"><span data-stu-id="c8541-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c8541-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8541-105">Description</span></span>  
 <span data-ttu-id="c8541-106">Procedimentos armazenados estendidos que foram registrados anteriormente sem um caminho completo para o nome de DLL podem não funcionar depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="c8541-106">Extended stored procedures that were previously registered without the full path for the DLL name may not work after you upgrade.</span></span> <span data-ttu-id="c8541-107">Isso é porque o diretório BINN antigo não é adicionado ao novo caminho durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="c8541-107">This is because the old BINN directory is not added to the new path during the upgrade process.</span></span> <span data-ttu-id="c8541-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode não conseguir localizar os procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="c8541-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not be able to locate the extended stored procedures.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c8541-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="c8541-109">Corrective Action</span></span>  
 <span data-ttu-id="c8541-110">Antes da atualização, faça as etapas a seguir para cada procedimento armazenado estendido que não foi registrado com um nome de caminho completo:</span><span class="sxs-lookup"><span data-stu-id="c8541-110">Before you upgrade, follow these steps for each extended stored procedure that was not registered with a full path name:</span></span>  
  
1.  <span data-ttu-id="c8541-111">Execute sp_dropextendedproc para remover o procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="c8541-111">Run sp_dropextendedproc to remove the extended stored procedure.</span></span>  
  
2.  <span data-ttu-id="c8541-112">Execute sp_addextendedproc para registrar o procedimento armazenado estendido com o nome de caminho completo.</span><span class="sxs-lookup"><span data-stu-id="c8541-112">Run sp_addextendedproc to register the extended stored procedure with the full path name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8541-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8541-113">See Also</span></span>  
 <span data-ttu-id="c8541-114">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c8541-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c8541-115">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="c8541-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
