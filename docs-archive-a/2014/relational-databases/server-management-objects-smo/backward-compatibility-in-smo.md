---
title: Compatibilidade com versões anteriores no SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 2f986436-aaf2-4eaf-9809-df849d97d4fb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73b6f4eebccf23850ccf08ec95ccb59dbc5c6293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573920"
---
# <a name="backward-compatibility-in-smo"></a><span data-ttu-id="cf8d9-102">Compatibilidade com versões anteriores no SMO</span><span class="sxs-lookup"><span data-stu-id="cf8d9-102">Backward Compatibility in SMO</span></span>
  <span data-ttu-id="cf8d9-103">Os aplicativos SMO que foram escritos em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser recompilados com o SMO no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf8d9-103">SMO applications that were written using previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be recompiled by using SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="migrating-smo-applications"></a><span data-ttu-id="cf8d9-104">Migrando aplicativos SMO</span><span class="sxs-lookup"><span data-stu-id="cf8d9-104">Migrating SMO Applications</span></span>  
 <span data-ttu-id="cf8d9-105">As referências a dlls do SMO em versões mais antigas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devem ser removidas, e as referências às novas dlls do SMO fornecidas com o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] devem ser incluídas.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-105">References to SMO dlls in older versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed, and references to the new SMO dlls that are provided with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be included.</span></span>  
  
 <span data-ttu-id="cf8d9-106">No mínimo, você faria as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="cf8d9-106">Minimally, you would reference the following:</span></span>  
  
-   <span data-ttu-id="cf8d9-107">Microsoft.SqlServer.ConnectionInfo</span><span class="sxs-lookup"><span data-stu-id="cf8d9-107">Microsoft.SqlServer.ConnectionInfo</span></span>  
  
-   <span data-ttu-id="cf8d9-108">Microsoft.SqlServer.Smo</span><span class="sxs-lookup"><span data-stu-id="cf8d9-108">Microsoft.SqlServer.Smo</span></span>  
  
-   <span data-ttu-id="cf8d9-109">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="cf8d9-109">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
 <span data-ttu-id="cf8d9-110">Esses arquivos são necessários para classes de conexão, classes de utilitário do SMO e classes de base.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-110">These files are required for connection classes, SMO utility classes, and foundation classes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf8d9-111">O arquivo SmoEnum.dll foi removido; portanto, as referências a ele devem ser removidas do projeto [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] SMO.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-111">SmoEnum.dll has been removed so references to it must be removed from the SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] project.</span></span>  
  
 <span data-ttu-id="cf8d9-112">Os namespaces também mudaram e você poderá usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf8d9-112">The namespaces have also changed, so you can use the following:</span></span>  
  
##### <a name="for-visual-c"></a><span data-ttu-id="cf8d9-113">Para o Visual C#</span><span class="sxs-lookup"><span data-stu-id="cf8d9-113">For Visual C#</span></span>  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
```  
  
##### <a name="for-visual-basic"></a><span data-ttu-id="cf8d9-114">Para o Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf8d9-114">For Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
```  
  
 <span data-ttu-id="cf8d9-115">Se o seu código usa a funcionalidade Urn, como `Server.GetSqlSmoObject(Urn)`, você deve estabelecer um vínculo com o namespace Microsoft.SqlServer.Management.Sdk.Sfc.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-115">If your code uses Urn functionality, such as `Server.GetSqlSmoObject(Urn)`, you must link to the Microsoft.SqlServer.Management.Sdk.Sfc namespace.</span></span>  
  
 <span data-ttu-id="cf8d9-116">Se o seu código usar o objeto Transfer diretamente, você deverá estabelecer um vínculo com o namespace Microsoft.SqlServer.Management.SmoExtended.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-116">If your code uses the Transfer object directly, you will have to link to the Microsoft.SqlServer.Management.SmoExtended namespace.</span></span>  
  
 <span data-ttu-id="cf8d9-117">Ao migrar o código, talvez seja necessário modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-117">When you migrate code, you might have to modify the code.</span></span> <span data-ttu-id="cf8d9-118">Isso ocorre porque vários recursos do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] foram preteridos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf8d9-118">This is because several [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] features have been deprecated in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="cf8d9-119">Para obter mais informações sobre recursos preteridos, consulte [recursos de mecanismo de banco de dados preteridos no SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) nos [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] manuais online do.</span><span class="sxs-lookup"><span data-stu-id="cf8d9-119">For more information about deprecated features, see [Deprecated Database Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
