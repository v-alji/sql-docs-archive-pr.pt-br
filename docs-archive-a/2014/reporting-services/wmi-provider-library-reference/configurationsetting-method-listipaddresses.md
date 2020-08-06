---
title: Método ListIPAddresses (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListIPAddresses method
ms.assetid: 7e7cf182-fba0-4604-a474-098461e23e9d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 845f7ba7db02a0b860f966184463580733af0faf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572914"
---
# <a name="listipaddresses-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6c125-102">Método ListIPAddresses (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6c125-102">ListIPAddresses Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6c125-103">Lista os endereços IP do computador do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="6c125-103">Lists the IP addresses for the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c125-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6c125-104">Syntax</span></span>  
  
```vb  
Public Sub ListIPAddresses (ByRef IPAddress() as String, _  
    ByRef IPVersion()as String, ByRef IsDhcpEnabled () as Boolean, _   
    ByRef Length as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListIPAddresses (out string[] IPAddress,   
    out string[] IPVersion, out bool[] isDhcpEnabled, out int length,   
    out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c125-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6c125-105">Parameters</span></span>  
 <span data-ttu-id="6c125-106">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="6c125-106">*IPAddress[]*</span></span>  
 <span data-ttu-id="6c125-107">[fora] A lista de endereços IP do computador.</span><span class="sxs-lookup"><span data-stu-id="6c125-107">[out] The list of IP address for the computer.</span></span>  
  
 <span data-ttu-id="6c125-108">*IPVersion[]*</span><span class="sxs-lookup"><span data-stu-id="6c125-108">*IPVersion[]*</span></span>  
 <span data-ttu-id="6c125-109">[out] A versão dos endereços IP.</span><span class="sxs-lookup"><span data-stu-id="6c125-109">[out] The version for the IP addresses.</span></span>  
  
 <span data-ttu-id="6c125-110">*IsDhcpEnabled[]*</span><span class="sxs-lookup"><span data-stu-id="6c125-110">*IsDhcpEnabled[]*</span></span>  
 <span data-ttu-id="6c125-111">[fora] Indica se os endereços IP são habilitados por DHCP.</span><span class="sxs-lookup"><span data-stu-id="6c125-111">[out] Indicates whether the IP addresses are DHCP enabled.</span></span>  
  
 <span data-ttu-id="6c125-112">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="6c125-112">*Length*</span></span>  
 <span data-ttu-id="6c125-113">[fora] O tamanho da matriz retornada pelo método.</span><span class="sxs-lookup"><span data-stu-id="6c125-113">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="6c125-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6c125-114">*HRESULT*</span></span>  
 <span data-ttu-id="6c125-115">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="6c125-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c125-116">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6c125-116">Return Value</span></span>  
 <span data-ttu-id="6c125-117">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="6c125-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6c125-118">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6c125-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c125-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="6c125-119">Remarks</span></span>  
 <span data-ttu-id="6c125-120">As cadeias de caracteres*IPVersion* são V4, V6.</span><span class="sxs-lookup"><span data-stu-id="6c125-120">*IPVersion* strings are V4, V6.</span></span>  
  
 <span data-ttu-id="6c125-121">Se *IsDhcpEnabled* for `True` , o *IPAddress* será dinâmico.</span><span class="sxs-lookup"><span data-stu-id="6c125-121">If *IsDhcpEnabled* is `True`, the *IPAddress* is dynamic.</span></span> <span data-ttu-id="6c125-122">Não deve ser usado para associações SSL.</span><span class="sxs-lookup"><span data-stu-id="6c125-122">It should not be used for SSL bindings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c125-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c125-123">Requirements</span></span>  
 <span data-ttu-id="6c125-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c125-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c125-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6c125-125">See Also</span></span>  
 [<span data-ttu-id="6c125-126">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6c125-126">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
