---
title: ICommandWithParameters | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 66644c70-def7-46d8-8c47-b883292a0288
author: rothja
ms.author: jroth
ms.openlocfilehash: df3103181b3cad772e7d1c73068b8864bf591b73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582439"
---
# <a name="icommandwithparameters"></a><span data-ttu-id="24b03-102">ICommandWithParameters</span><span class="sxs-lookup"><span data-stu-id="24b03-102">ICommandWithParameters</span></span>
  <span data-ttu-id="24b03-103">Aprimoramentos no mecanismo de banco de dados desde o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permitem que ICommandWithParameters::GetParameterInfo obtenha descrições mais precisas dos resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="24b03-103">Improvements in the database engine beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ICommandWithParameters::GetParameterInfo to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="24b03-104">Esses resultados mais precisos podem ser diferentes dos valores retornados por CommandWithParameters::GetParameterInfo em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24b03-104">These more accurate results may differ from the values returned by CommandWithParameters::GetParameterInfo in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="24b03-105">Para obter mais informações, veja [Descoberta de metadados](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="24b03-105">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="24b03-106">Além disso, do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] em diante, ao chamar ICommandWithParameters::SetParameterInfo, o valor passado para o parâmetro *pwszName* precisa ser um identificador válido.</span><span class="sxs-lookup"><span data-stu-id="24b03-106">Also beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], when calling ICommandWithParameters::SetParameterInfo, the value passed to the *pwszName* parameter must be a valid identifier.</span></span> <span data-ttu-id="24b03-107">Para obter mais informações, consulte [Database Identifiers](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="24b03-107">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b03-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24b03-108">See Also</span></span>  
 [<span data-ttu-id="24b03-109">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="24b03-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
