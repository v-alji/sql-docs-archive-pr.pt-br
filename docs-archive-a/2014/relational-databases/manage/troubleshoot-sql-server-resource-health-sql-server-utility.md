---
title: Solucionar problemas de integridade de recursos do SQL Server (Utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 182225dd618dd1e9e058c549bdc07818813ba764
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570688"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a><span data-ttu-id="976ba-102">Solucionar problemas de integridade de recursos do SQL Server (Utilitário do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="976ba-102">Troubleshoot SQL Server Resource Health (SQL Server Utility)</span></span>
  <span data-ttu-id="976ba-103">Solucionar problemas de integridade de recursos identificados por uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP pode incluir a eliminação de uma CPU sobrecarregada em um computador ou em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou a eliminação uma CPU sobrecarregada para um aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="976ba-103">Troubleshooting resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP might include mitigating overutilized CPU on a computer or on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or mitigating overutilized CPU for a data-tier application.</span></span> <span data-ttu-id="976ba-104">Outros problemas incluem a resolução de espaço de arquivo superutilizado para arquivos de banco de dados ou a resolução de superutilização de espaço em disco alocado em um volume de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="976ba-104">Other issues might include resolving overutilized file space for database files or resolving overutilization of allocated disk space on a storage volume.</span></span>  
  
 <span data-ttu-id="976ba-105">Note que, se um banco de dados estiver no estado de "emergência", o estado de integridade exibirá o espaço de arquivo de log superutilizado.</span><span class="sxs-lookup"><span data-stu-id="976ba-105">Note that if a database is in "emergency" state, the health state will display overutilized log file space.</span></span>  
  
 <span data-ttu-id="976ba-106">Para obter mais informações sobre a coleta de dados com falha que resulta em ícones de status cinza na exibição de lista da instância gerenciada em um UCP, veja [Recursos e tarefas do Utilitário do SQL Server](../../database-engine/troubleshoot-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="976ba-106">For more information about failed data collection resulting in gray status icons in the managed instance list view on a UCP, see [Troubleshoot the SQL Server Utility](../../database-engine/troubleshoot-the-sql-server-utility.md).</span></span> <span data-ttu-id="976ba-107">Para obter mais informações sobre como começar a usar o Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , veja [Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="976ba-107">For more information about getting started with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="976ba-108">Para obter mais informações sobre como eliminar problemas de integridade de recursos específicos identificados por um UCP do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="976ba-108">For more information about mitigating specific resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, see the following topics:</span></span>  
  
-   [<span data-ttu-id="976ba-109">Como identificar sua versão de SQL Server e edição</span><span class="sxs-lookup"><span data-stu-id="976ba-109">How to identify your SQL Server version and edition</span></span>](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [<span data-ttu-id="976ba-110">Solucionando problemas de desempenho no SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="976ba-110">Troubleshooting Performance Problems in SQL Server 2008</span></span>](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
