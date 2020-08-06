---
title: Iniciador do Daemon de Filtro de Texto Completo do SQL (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d0dc03db-5f76-4558-b041-1ac7b9b5bb16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45194c893db048151cdb03d33f1419ef42246d69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568989"
---
# <a name="sql-full-text-filter-daemon-launcher-sql-server-configuration-manager"></a><span data-ttu-id="ed477-102">Iniciador do Daemon de Filtro de Texto Completo do SQL (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="ed477-102">SQL Full-text Filter Daemon Launcher (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="ed477-103">A partir do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], o serviço do Iniciador do Daemon de Filtro de Texto Completo do SQL (Iniciador FDHOST) é usado pela pesquisa de texto completo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para iniciar o processo do host do daemon de filtro que manipula a filtragem da pesquisa de texto completo e a quebra de palavras.</span><span class="sxs-lookup"><span data-stu-id="ed477-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search to start the filter daemon host process, which handles full-text search filtering and word breaking.</span></span> <span data-ttu-id="ed477-104">Esse serviço deve estar em execução para usar a pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ed477-104">This service must be running to use full-text search.</span></span> <span data-ttu-id="ed477-105">O Iniciador FDHOST é um serviço de reconhecimento de instâncias associado a uma instância específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed477-105">The FDHOST Launcher service is an instance-aware service that is associated with a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ed477-106">O serviço do Iniciador FDHOST propaga as informações da conta de serviço para cada processo do host do daemon de filtro iniciado.</span><span class="sxs-lookup"><span data-stu-id="ed477-106">The FDHOST Launcher service propagates the service account information to each filter daemon host process started.</span></span> <span data-ttu-id="ed477-107">Para obter informações sobre os processos do host do daemon de filtro, consulte "Arquitetura da pesquisa de texto completo" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed477-107">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
