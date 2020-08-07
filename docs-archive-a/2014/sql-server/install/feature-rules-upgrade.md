---
title: Regras de recurso (atualização) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 653b15db-a984-4b4b-b224-81b0285b099b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0527c1ba26fed86a6c1a3d3a2ea7c11b096474f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576185"
---
# <a name="feature-rules-upgrade"></a><span data-ttu-id="8e51b-102">Regras de recurso (atualizar)</span><span class="sxs-lookup"><span data-stu-id="8e51b-102">Feature Rules (Upgrade)</span></span>
  <span data-ttu-id="8e51b-103">A Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valida a configuração do computador antes da conclusão da operação de Instalação.</span><span class="sxs-lookup"><span data-stu-id="8e51b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="8e51b-104">Durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o sistema verifica o computador onde o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será instalado e verifica as condições que impedem uma operação bem-sucedida de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e51b-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the system scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed and checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="8e51b-105">Antes que a Instalação inicie o assistente de atualização, ele recupera o status de cada item.</span><span class="sxs-lookup"><span data-stu-id="8e51b-105">Before Setup starts the upgrade wizard, it retrieves the status of each item.</span></span> <span data-ttu-id="8e51b-106">Em seguida, compara o resultado com condições necessárias e fornece orientação para a remoção de problemas de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="8e51b-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="8e51b-107">A verificação da configuração do sistema gera um relatório que contém uma breve descrição de cada regra executada, bem como o status de execução.</span><span class="sxs-lookup"><span data-stu-id="8e51b-107">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="8e51b-108">O relatório de verificação da configuração do sistema está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="8e51b-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="8e51b-109">Antes de executar a operação de instalação, reveja os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8e51b-109">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="8e51b-110">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8e51b-110">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="8e51b-111">Recursos com suporte nas edições do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8e51b-111">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="8e51b-112">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e51b-112">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="8e51b-113">Versões de idiomas locais no SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e51b-113">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="8e51b-114">Outras referências:</span><span class="sxs-lookup"><span data-stu-id="8e51b-114">Other references:</span></span>  
  
1.  [<span data-ttu-id="8e51b-115">Atualizações de versão e edição com suporte</span><span class="sxs-lookup"><span data-stu-id="8e51b-115">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="8e51b-116">Antes de instalar o cluster de failover</span><span class="sxs-lookup"><span data-stu-id="8e51b-116">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e51b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e51b-117">See Also</span></span>  
 [<span data-ttu-id="8e51b-118">Normas de instalação</span><span class="sxs-lookup"><span data-stu-id="8e51b-118">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
