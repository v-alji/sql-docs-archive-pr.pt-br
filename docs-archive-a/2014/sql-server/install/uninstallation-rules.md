---
title: Regras de desinstalação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 07554612-8cb6-4bd9-adde-956177261ccd
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c2e1c3e2e36177053a43b032dd4721dc503fa20c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573433"
---
# <a name="uninstallation-rules"></a><span data-ttu-id="aaa23-102">Regras de desinstalação</span><span class="sxs-lookup"><span data-stu-id="aaa23-102">Uninstallation rules</span></span>
  <span data-ttu-id="aaa23-103">A página Regras de Desinstalação executa um conjunto de regras para garantir que a operação de Instalação pode ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="aaa23-103">The Uninstallation Rules page will run a set of rules to ensure that the Setup operation can complete successfully.</span></span>  
  
 <span data-ttu-id="aaa23-104">A Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valida a configuração do computador antes da conclusão da operação de Instalação.</span><span class="sxs-lookup"><span data-stu-id="aaa23-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="aaa23-105">Durante a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC (Verificador de Configuração do Sistema) examina o computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será instalado.</span><span class="sxs-lookup"><span data-stu-id="aaa23-105">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="aaa23-106">O SCC verifica se existem condições que impedem uma operação de instalação com êxito do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaa23-106">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="aaa23-107">Antes que a Instalação inicie o assistente de desinstalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC recupera o status de cada item.</span><span class="sxs-lookup"><span data-stu-id="aaa23-107">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uninstallation wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="aaa23-108">Em seguida, compara o resultado com condições necessárias e fornece orientação para a remoção de problemas de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="aaa23-108">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="aaa23-109">A verificação da configuração do sistema gera um relatório que contém uma breve descrição de cada regra executada, bem como o status de execução.</span><span class="sxs-lookup"><span data-stu-id="aaa23-109">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="aaa23-110">O relatório de verificação da configuração do sistema está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="aaa23-110">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="aaa23-111">Antes de executar a operação de instalação, reveja os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="aaa23-111">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="aaa23-112">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="aaa23-112">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="aaa23-113">Recursos com suporte nas edições do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="aaa23-113">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="aaa23-114">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="aaa23-114">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="aaa23-115">Versões de idiomas locais no SQL Server</span><span class="sxs-lookup"><span data-stu-id="aaa23-115">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="aaa23-116">Outras referências:</span><span class="sxs-lookup"><span data-stu-id="aaa23-116">Other references:</span></span>  
  
1.  [<span data-ttu-id="aaa23-117">Atualizações de versão e edição com suporte</span><span class="sxs-lookup"><span data-stu-id="aaa23-117">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="aaa23-118">Antes de instalar o cluster de failover</span><span class="sxs-lookup"><span data-stu-id="aaa23-118">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="aaa23-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aaa23-119">See Also</span></span>  
 [<span data-ttu-id="aaa23-120">Normas de instalação</span><span class="sxs-lookup"><span data-stu-id="aaa23-120">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
