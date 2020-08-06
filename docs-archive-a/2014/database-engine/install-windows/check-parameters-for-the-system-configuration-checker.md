---
title: Verificar parâmetros do Verificador de Configuração do Sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, system configuration checks
- failed system configuration checks [SQL Server]
- verifying configuration before installation
- SCC [SQL Server]
- system configuration checker
- scanning computer before installation [SQL Server]
- checking configuration before installation
- status information [SQL Server], system configuration checker
- parameters [SQL Server], system configuration checker
- configuration checkers [SQL Server]
- Setup [SQL Server], system configuration checker
ms.assetid: 8e712c15-6bfa-4d71-b303-9526101e5594
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bf159d3c6184974d108075cd65e32b449d441bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681831"
---
# <a name="check-parameters-for-the-system-configuration-checker"></a><span data-ttu-id="459f1-102">Verificar parâmetros do Verificador de Configuração do Sistema</span><span class="sxs-lookup"><span data-stu-id="459f1-102">Check Parameters for the System Configuration Checker</span></span>
  <span data-ttu-id="459f1-103">Durante a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC (Verificador de Configuração do Sistema) examina o computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será instalado.</span><span class="sxs-lookup"><span data-stu-id="459f1-103">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="459f1-104">O SCC verifica se existem condições que impedem uma instalação com êxito do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="459f1-104">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="459f1-105">Antes que a Instalação inicie o Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC recupera o status de cada item.</span><span class="sxs-lookup"><span data-stu-id="459f1-105">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="459f1-106">Em seguida, compara o resultado com condições necessárias e fornece orientação para a remoção de problemas de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="459f1-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="459f1-107">O verificador da configuração do sistema gera um relatório que contém uma breve descrição de cada regra executada, bem como o status de execução.</span><span class="sxs-lookup"><span data-stu-id="459f1-107">The system configuration checker generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="459f1-108">O relatório de verificação da configuração do sistema está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="459f1-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459f1-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="459f1-109">See Also</span></span>  
 <span data-ttu-id="459f1-110">[Requisitos de hardware e software para a instalação do SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="459f1-110">[Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 <span data-ttu-id="459f1-111">[Considerações de segurança para uma instalação do SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="459f1-111">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="459f1-112">Atualizações de versão e edição com suporte</span><span class="sxs-lookup"><span data-stu-id="459f1-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
  
