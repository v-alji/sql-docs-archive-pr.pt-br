---
title: Registro em log para pacotes com balanceamento de carga em servidores remotos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], remote packages
ms.assetid: fd571567-b625-4f9a-8b7e-42c5c588b11b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b45fa6607d6edc1559d8ebcbbbc7598e11eac408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574110"
---
# <a name="logging-for-load-balanced-packages-on-remote-servers"></a><span data-ttu-id="0efa8-102">Log para carga de pacotes balanceados em servidores remotos</span><span class="sxs-lookup"><span data-stu-id="0efa8-102">Logging for Load Balanced Packages on Remote Servers</span></span>
  <span data-ttu-id="0efa8-103">É mais fácil para um administrador gerenciar os logs de todos os pacotes filho que estão sendo executados em vários servidores quando todos os pacotes filho usam o mesmo provedor de log e todos gravam no mesmo destino.</span><span class="sxs-lookup"><span data-stu-id="0efa8-103">It is easier for an administrator to manage the logs for all the child packages that are running on various servers when all the child packages use the same log provider and they all write to the same destination.</span></span> <span data-ttu-id="0efa8-104">Um modo para criar um arquivo de log comum para todos os pacotes filho é configurar os pacotes filho para registrar os seus eventos em um provedor de log SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0efa8-104">One way that you can create a common log file for all child packages is to configure the child packages to log their events to a SQL Server log provider.</span></span> <span data-ttu-id="0efa8-105">Você pode configurar todos os pacotes para usarem o mesmo banco de dados, o mesmo servidor e a mesma instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="0efa8-105">You can configure all the packages to use the same database, the same server, and the same instance of the server.</span></span>  
  
 <span data-ttu-id="0efa8-106">Para exibir os arquivos de log, o administrador precisa apenas fazer logon em um único servidor para exibir os arquivos de log de todos os pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="0efa8-106">To view the log files, the administrator only has to log on to a single server to view the log files for all child packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0efa8-107">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0efa8-107">Related Tasks</span></span>  
 <span data-ttu-id="0efa8-108">Para obter informações sobre como habilitar o log em um pacote, consulte [Habilitar log de pacote no SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0efa8-108">For information about how to enable logging in a package, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0efa8-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0efa8-109">See Also</span></span>  
 [<span data-ttu-id="0efa8-110">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0efa8-110">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
