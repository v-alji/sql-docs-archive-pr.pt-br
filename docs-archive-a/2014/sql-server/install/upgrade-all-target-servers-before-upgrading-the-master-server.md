---
title: Atualizar todos os servidores de destino antes de atualizar o servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TSX [SQL Server Agent]
- target servers [SQL Server Agent]
- MSX [SQL Server Agent]
- master servers [SQL Server Agent]
ms.assetid: 2c231793-3878-4a5e-a425-1fa0d787ba84
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 031fedc4af4b058704cef1da8df846397b235305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569822"
---
# <a name="upgrade-all-target-servers-before-upgrading-the-master-server"></a><span data-ttu-id="07ab3-102">Atualizar todos os servidores de destino antes da atualização do servidor mestre</span><span class="sxs-lookup"><span data-stu-id="07ab3-102">Upgrade all target servers before upgrading the master server</span></span>
  <span data-ttu-id="07ab3-103">Antes de você atualizar o servidor mestre, atualize todos os computadores que estão executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e estão configurados como servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="07ab3-103">Before you upgrade the master server, upgrade all computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are configured as target servers.</span></span>  
  
## <a name="component"></a><span data-ttu-id="07ab3-104">Componente</span><span class="sxs-lookup"><span data-stu-id="07ab3-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="07ab3-105">Agent</span><span class="sxs-lookup"><span data-stu-id="07ab3-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="07ab3-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="07ab3-106">Description</span></span>  
 <span data-ttu-id="07ab3-107">Para automatizar a administração em ambientes com vários servidores, é necessário ter pelo menos um servidor mestre e um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="07ab3-107">To automate administration in multiserver environments, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="07ab3-108">Um servidor mestre distribui trabalhos para servidores de destino e também recebe eventos desses servidores.</span><span class="sxs-lookup"><span data-stu-id="07ab3-108">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="07ab3-109">Ele também armazena a cópia central das definições de trabalho para trabalhos que são executados em servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="07ab3-109">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span>  
  
 <span data-ttu-id="07ab3-110">Se o servidor atual estiver configurado como servidor mestre, atualize todos os seus servidores de destino antes de atualizar o servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="07ab3-110">If the current server is configured as a master server, upgrade all of your target servers first before you upgrade the master server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="07ab3-111">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="07ab3-111">Corrective Action</span></span>  
 <span data-ttu-id="07ab3-112">Se não for possível atualizar todos os servidores de destino antes de atualizar o servidor mestre, você deve remover todos os servidores de destino e reinscrevê-los depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="07ab3-112">If you cannot upgrade all target servers before you upgrade the master server, you must defect all target servers and reenlist them after you upgrade.</span></span>  
  
 <span data-ttu-id="07ab3-113">Para obter mais informações, consulte os tópicos ‘Automatizando a administração em uma empresa’, "Como remover um servidor de destino de um servidor mestre’ e ‘Como inscrever um servidor de destino em um mestre’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07ab3-113">For more information, see the topics "Automating Administration across an Enterprise," "How to: Defect a Target Server from a Master Server," and "How to: Enlist a Target Server to a Master" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ab3-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07ab3-114">See Also</span></span>  
 <span data-ttu-id="07ab3-115">[Problemas de atualização do SQL Server Agent](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="07ab3-115">[SQL Server Agent Upgrade Issues](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="07ab3-116">Problemas de atualização do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="07ab3-116">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
