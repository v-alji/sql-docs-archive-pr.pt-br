---
title: Configurar seu data warehouse do ponto de controle do utilitário (Utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60b9623b468f2763cf619c325412373e3603f3a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570694"
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a><span data-ttu-id="92383-102">Configurar o data warehouse a partir do ponto de controle do utilitário (Utilitário do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="92383-102">Configure Your Utility Control Point Data Warehouse (SQL Server Utility)</span></span>
  <span data-ttu-id="92383-103">Dados coletados por instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são armazenados no UMDW (data warehouse de gerenciamento do utilitário); o nome de arquivo UMDW é sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="92383-103">Data collected by managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are stored in the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="92383-104">É possível configurar o período de retenção de dados do UMDW.</span><span class="sxs-lookup"><span data-stu-id="92383-104">You can configure the UMDW data retention period.</span></span> <span data-ttu-id="92383-105">Para obter mais informações, veja [Administração do Utilitário &#40;Utilitário do SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="92383-105">For more information, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="92383-106">Os parâmetros de configuração a seguir não podem ser configurados nesta versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="92383-106">The following configuration settings are not configurable in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="92383-107">Nome do UMDW: Sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="92383-107">UMDW name: Sysutility_mdw.</span></span>  
  
-   <span data-ttu-id="92383-108">Frequência de upload do conjunto de coleta: a cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="92383-108">Collection set upload frequency: Every 15 minutes.</span></span>  
  
 <span data-ttu-id="92383-109">O diretório do UMDW é configurável: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<Nome_do_UCP>\MSSQL\Data\\, em que \<System drive>, normalmente, é a unidade C:\.</span><span class="sxs-lookup"><span data-stu-id="92383-109">The UMDW directory is configurable: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, where \<System drive> is normally the C:\ drive.</span></span> <span data-ttu-id="92383-110">O arquivo de log Sysutility_mdw_\<GUID>_LOG está localizado no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="92383-110">The log file, Sysutility_mdw_\<GUID>_LOG, is located in the same directory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92383-111">O local do arquivo UMDW (sysutility_mdw) pode ser alterado usando-se desanexar/anexar ou ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="92383-111">The UMDW (sysutility_mdw) file location can be changed using detach/attach or ALTER DATABASE.</span></span> <span data-ttu-id="92383-112">É recomendável usar ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="92383-112">We recommend the use of ALTER DATABASE.</span></span> <span data-ttu-id="92383-113">Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92383-113">For more information see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92383-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92383-114">See Also</span></span>  
 [<span data-ttu-id="92383-115">Recursos e tarefas do utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="92383-115">SQL Server Utility Features and Tasks</span></span>](sql-server-utility-features-and-tasks.md)  
  
  
