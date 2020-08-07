---
title: O serviço de SQL Server Agent não pode usar a autenticação SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- authentication [SQL Server Agent]
- SQL Server Authentication [SQL Server Agent]
ms.assetid: c39f3ec3-fc2c-4c12-940f-60d8d3d17660
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 32188b1c47168aefbca914fa15f71850df716153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575558"
---
# <a name="sql-server-agent-service-cannot-use-sql-server-authentication"></a><span data-ttu-id="46585-102">Serviço do SQL Server Agent não pode usar a Autenticação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="46585-102">SQL Server Agent Service cannot use SQL Server Authentication</span></span>
  <span data-ttu-id="46585-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent aceita Autenticação do Windows somente quando o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent conecta-se com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46585-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent only supports Windows Authentication when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="46585-104">Componente</span><span class="sxs-lookup"><span data-stu-id="46585-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="46585-105">Agent</span><span class="sxs-lookup"><span data-stu-id="46585-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="46585-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="46585-106">Description</span></span>  
 <span data-ttu-id="46585-107">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent somente pode fazer logon no banco de dados usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="46585-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can only log on to the database using Windows Authentication.</span></span> <span data-ttu-id="46585-108">Isso significa que a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser um usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46585-108">This means that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account must be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="46585-109">Para obter mais informações, consulte os tópicos ‘Segurança para administração automática’ e ‘Implementando segurança no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46585-109">For more information, see the topics "Security for Automatic Administration" and "Implementing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Security" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46585-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46585-110">See Also</span></span>  
 [<span data-ttu-id="46585-111">Problemas de atualização do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="46585-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
