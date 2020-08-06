---
title: Instalar a Replicação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- components [SQL Server replication]
- command line installations [SQL Server replication]
- installing replication
- replication [SQL Server], installing
- command prompt [SQL Server replication]
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ba941fda1d463e7bb4a26bd2fbb45d2a82ca27b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679496"
---
# <a name="install-sql-server-replication"></a><span data-ttu-id="e3d89-102">Instalar a Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3d89-102">Install SQL Server Replication</span></span>
  <span data-ttu-id="e3d89-103">É possível instalar componentes de replicação usando o Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e3d89-103">Replication components can be installed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or at a command prompt.</span></span> <span data-ttu-id="e3d89-104">Instale a replicação ao instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou ao modificar uma instância existente.</span><span class="sxs-lookup"><span data-stu-id="e3d89-104">Install replication when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or when you modify an existing instance.</span></span>  
  
 <span data-ttu-id="e3d89-105">Depois da instalação dos componentes de replicação, é necessário configurar o servidor antes de usar a replicação.</span><span class="sxs-lookup"><span data-stu-id="e3d89-105">After replication components are installed, you must configure the server before you can use replication.</span></span> <span data-ttu-id="e3d89-106">Para obter mais informações, veja [Configurar distribuição](../../relational-databases/replication/configure-distribution.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3d89-106">For more information, see [Configure Distribution](../../relational-databases/replication/configure-distribution.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e3d89-107">Se você instalar componentes de replicação ao modificar uma instância existente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é necessário parar e reiniciar o agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="e3d89-107">If you install replication components when you modify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent after the installation is completed.</span></span> <span data-ttu-id="e3d89-108">Essa ação ajuda a assegurar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent reconheça os subsistemas de agente de replicação e possa chamar agentes de replicação em etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e3d89-108">This action helps ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent recognizes the replication agent subsystems and can call replication agents from job steps.</span></span>  
  
## <a name="installing-replication-by-using-setup"></a><span data-ttu-id="e3d89-109">Instalando a replicação com o uso de instalação</span><span class="sxs-lookup"><span data-stu-id="e3d89-109">Installing Replication by Using Setup</span></span>  
 <span data-ttu-id="e3d89-110">**Para instalar a replicação ao instalar uma nova instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e3d89-110">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="e3d89-111">Para instalar componentes de replicação, incluindo o RMO (Replication Management Objects), selecione **SQL Server Replication** na página **Seleção de Recursos** do Assistente de Instalação.</span><span class="sxs-lookup"><span data-stu-id="e3d89-111">To install replication components, including Replication Management Objects (RMO), select **SQL Server Replication** on the **Feature Selection** page of the Installation Wizard.</span></span>  
  
## <a name="installing-replication-from-the-command-prompt"></a><span data-ttu-id="e3d89-112">Instalando a replicação a partir do prompt de comando</span><span class="sxs-lookup"><span data-stu-id="e3d89-112">Installing Replication from the Command Prompt</span></span>  
 <span data-ttu-id="e3d89-113">**Para instalar a replicação ao instalar uma nova instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e3d89-113">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="e3d89-114">Consulte [instalar SQL Server 2014 no prompt de comando](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="e3d89-114">See [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d89-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3d89-115">See Also</span></span>  
 <span data-ttu-id="e3d89-116">[Instalar o SQL Server 2014](install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e3d89-116">[Install SQL Server 2014](install-sql-server.md) </span></span>  
 <span data-ttu-id="e3d89-117">[Instalar o SQL Server 2014 no prompt de comando](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="e3d89-117">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 [<span data-ttu-id="e3d89-118">Recursos com suporte nas edições do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e3d89-118">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
