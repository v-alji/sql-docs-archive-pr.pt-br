---
title: Assistente de cluster de failover do SQL Server-concluído | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 820f35b7-a3cd-46c9-9963-811633d0711a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0820f3a70cfc441cc79c0939f78eb4306d375fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576134"
---
# <a name="sql-server-failover-cluster-wizard---complete"></a><span data-ttu-id="6179f-102">Assistente de cluster de failover do SQL Server - Conclusão</span><span class="sxs-lookup"><span data-stu-id="6179f-102">SQL Server Failover Cluster Wizard - Complete</span></span>
  <span data-ttu-id="6179f-103">A Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valida a configuração do computador antes da conclusão da operação de Instalação.</span><span class="sxs-lookup"><span data-stu-id="6179f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="6179f-104">Durante a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC (Verificador de Configuração do Sistema) examina o computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será instalado.</span><span class="sxs-lookup"><span data-stu-id="6179f-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="6179f-105">O SCC verifica se existem condições que impedem uma operação de instalação com êxito do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6179f-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="6179f-106">Antes que a Instalação inicie o Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC recupera o status de cada item.</span><span class="sxs-lookup"><span data-stu-id="6179f-106">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="6179f-107">Em seguida, compara o resultado com condições necessárias e fornece orientação para a remoção de problemas de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="6179f-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="6179f-108">A verificação da configuração do sistema gera um relatório que contém uma breve descrição de cada regra executada, bem como o status de execução.</span><span class="sxs-lookup"><span data-stu-id="6179f-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="6179f-109">O relatório de verificação da configuração do sistema está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6179f-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="6179f-110">Antes de executar a operação de instalação, reveja os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6179f-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="6179f-111">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6179f-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="6179f-112">Recursos com suporte nas edições do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6179f-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="6179f-113">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6179f-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="6179f-114">Versões de idiomas locais no SQL Server</span><span class="sxs-lookup"><span data-stu-id="6179f-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="6179f-115">Outras referências:</span><span class="sxs-lookup"><span data-stu-id="6179f-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="6179f-116">Atualizações de versão e edição com suporte</span><span class="sxs-lookup"><span data-stu-id="6179f-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="6179f-117">Antes de instalar o cluster de failover</span><span class="sxs-lookup"><span data-stu-id="6179f-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="6179f-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6179f-118">See Also</span></span>  
 [<span data-ttu-id="6179f-119">Normas de instalação</span><span class="sxs-lookup"><span data-stu-id="6179f-119">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
