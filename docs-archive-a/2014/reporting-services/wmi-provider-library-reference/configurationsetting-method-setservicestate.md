---
title: Método SetServiceState (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683988"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c80dd-102">Método SetServiceState (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c80dd-102">SetServiceState Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c80dd-103">Ativa e desativa o Servidor de Relatório do Windows e os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="c80dd-103">Turns the Report Server Windows and Web services on and off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c80dd-104">Syntax</span></span>  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c80dd-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="c80dd-105">Parameters</span></span>  
 <span data-ttu-id="c80dd-106">*EnableWindowsService*</span><span class="sxs-lookup"><span data-stu-id="c80dd-106">*EnableWindowsService*</span></span>  
 <span data-ttu-id="c80dd-107">Um valor `Boolean` que indica o estado do serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="c80dd-107">A `Boolean` value indicating the state of the Windows service.</span></span> <span data-ttu-id="c80dd-108">Um valor `true` inicia o serviço Servidor de Relatório do Windows; um valor `false` interrompe o serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="c80dd-108">A value of `true` starts the Report Server Windows service; a value of `false` stops the Windows service.</span></span>  
  
 <span data-ttu-id="c80dd-109">*EnableWebService*</span><span class="sxs-lookup"><span data-stu-id="c80dd-109">*EnableWebService*</span></span>  
 <span data-ttu-id="c80dd-110">Um `Boolean` valor que indica o estado do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] serviço Web.</span><span class="sxs-lookup"><span data-stu-id="c80dd-110">A `Boolean` value indicating the state of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web service.</span></span> <span data-ttu-id="c80dd-111">Um valor `true` inicia o serviço Web Servidor de Relatórios; um valor `false` interrompe o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="c80dd-111">A value of `true` starts the Report Server Web service; a value of `false` stops the Web service</span></span>  
  
 <span data-ttu-id="c80dd-112">*EnableReportManager*</span><span class="sxs-lookup"><span data-stu-id="c80dd-112">*EnableReportManager*</span></span>  
 <span data-ttu-id="c80dd-113">Um valor `Boolean` que indica o estado desejado do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="c80dd-113">A `Boolean` value indicating the desired state of the Report manager.</span></span>  
  
 <span data-ttu-id="c80dd-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c80dd-114">*HRESULT*</span></span>  
 <span data-ttu-id="c80dd-115">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="c80dd-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c80dd-116">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="c80dd-116">Return Value</span></span>  
 <span data-ttu-id="c80dd-117">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="c80dd-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="c80dd-118">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="c80dd-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="c80dd-119">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="c80dd-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c80dd-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="c80dd-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c80dd-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c80dd-121">Requirements</span></span>  
 <span data-ttu-id="c80dd-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80dd-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80dd-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c80dd-123">See Also</span></span>  
 [<span data-ttu-id="c80dd-124">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c80dd-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
