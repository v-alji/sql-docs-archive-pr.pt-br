---
title: bcp_getcolfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_getcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_getcolfmt function
ms.assetid: f8bdada5-7b2d-4475-8c98-f93e9d77b130
author: rothja
ms.author: jroth
ms.openlocfilehash: aabc811a5aa0babe5119c4ef0ed0e649586d73cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572064"
---
# <a name="bcp_getcolfmt"></a><span data-ttu-id="a55e1-102">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="a55e1-102">bcp_getcolfmt</span></span>
  <span data-ttu-id="a55e1-103">Usado para localizar o valor da propriedade de formato da coluna.</span><span class="sxs-lookup"><span data-stu-id="a55e1-103">Used to find the column format property value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55e1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a55e1-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_getcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbvalue,  
INT*   
pcbLen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a55e1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a55e1-105">Arguments</span></span>  
 <span data-ttu-id="a55e1-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="a55e1-106">*hdbc*</span></span>  
 <span data-ttu-id="a55e1-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="a55e1-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="a55e1-108">*campo*</span><span class="sxs-lookup"><span data-stu-id="a55e1-108">*field*</span></span>  
 <span data-ttu-id="a55e1-109">É o número de coluna para o qual a propriedade é recuperada.</span><span class="sxs-lookup"><span data-stu-id="a55e1-109">Is the column number for which the property is retrieved.</span></span>  
  
 <span data-ttu-id="a55e1-110">*property*</span><span class="sxs-lookup"><span data-stu-id="a55e1-110">*property*</span></span>  
 <span data-ttu-id="a55e1-111">É um das constantes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="a55e1-111">Is one of the property constants.</span></span>  
  
 <span data-ttu-id="a55e1-112">*Valores*</span><span class="sxs-lookup"><span data-stu-id="a55e1-112">*pValue*</span></span>  
 <span data-ttu-id="a55e1-113">É o ponteiro para o buffer do qual recuperar o valor dado propriedade.</span><span class="sxs-lookup"><span data-stu-id="a55e1-113">Is the pointer to the buffer from which to retrieve the property value.</span></span>  
  
 <span data-ttu-id="a55e1-114">*cbValue*</span><span class="sxs-lookup"><span data-stu-id="a55e1-114">*cbValue*</span></span>  
 <span data-ttu-id="a55e1-115">É o comprimento do buffer da propriedade em bytes.</span><span class="sxs-lookup"><span data-stu-id="a55e1-115">Is the length of the property buffer in bytes.</span></span>  
  
 <span data-ttu-id="a55e1-116">*pcbLen*</span><span class="sxs-lookup"><span data-stu-id="a55e1-116">*pcbLen*</span></span>  
 <span data-ttu-id="a55e1-117">Ponteiro para o comprimento dos dados que estão sendo retornados no buffer de propriedade.</span><span class="sxs-lookup"><span data-stu-id="a55e1-117">Pointer to length of the data that is being returned in the property buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a55e1-118">Retornos</span><span class="sxs-lookup"><span data-stu-id="a55e1-118">Returns</span></span>  
 <span data-ttu-id="a55e1-119">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="a55e1-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a55e1-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="a55e1-120">Remarks</span></span>  
 <span data-ttu-id="a55e1-121">Valores da propriedade de formato da coluna são listados no tópico [bcp_setcolfmt](bcp-setcolfmt.md) .</span><span class="sxs-lookup"><span data-stu-id="a55e1-121">Column format property values are listed in the [bcp_setcolfmt](bcp-setcolfmt.md) topic.</span></span> <span data-ttu-id="a55e1-122">Os valores de propriedade da coluna são definidos chamando a função **bcp_setcolfmt** e a função **bcp_getcolfmt** é usada para localizar o valor da propriedade de formato da coluna.</span><span class="sxs-lookup"><span data-stu-id="a55e1-122">The column format property values are set by calling the **bcp_setcolfmt** function, and the **bcp_getcolfmt** function is used to find the column format property value.</span></span>  
  
 <span data-ttu-id="a55e1-123">Podem ser observadas alterações de comportamento ao conectar a um computador de servidor [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (ou posterior), na comparação com versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a55e1-123">Behavior changes may be observed when connecting to a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (or later) server computer, compared to earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions.</span></span> <span data-ttu-id="a55e1-124">Para obter mais informações, veja [Descoberta de metadados](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="a55e1-124">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="bcp_getcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a55e1-125">Suporte de bcp_getcolfmt a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="a55e1-125">bcp_getcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a55e1-126">Os tipos usados com a `BCP_FMT_TYPE` propriedade para tipos de data/hora são os especificados em [alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a55e1-126">The types used with the `BCP_FMT_TYPE` property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="a55e1-127">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a55e1-127">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55e1-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a55e1-128">See Also</span></span>  
 [<span data-ttu-id="a55e1-129">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="a55e1-129">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
