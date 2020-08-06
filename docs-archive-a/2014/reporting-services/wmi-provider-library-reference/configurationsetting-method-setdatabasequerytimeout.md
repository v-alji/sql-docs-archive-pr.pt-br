---
title: Método SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683995"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4be06-102">Método SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="4be06-102">SetDatabaseQueryTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4be06-103">Especifica o valor de tempo limite padrão para consultas no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4be06-103">Specifies the default time-out value for report server database queries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be06-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4be06-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4be06-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="4be06-105">Parameters</span></span>  
 <span data-ttu-id="4be06-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="4be06-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="4be06-107">O valor de tempo limite padrão, em segundos, para as consultas do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4be06-107">The default timeout value, in seconds, for report server database queries.</span></span>  
  
 <span data-ttu-id="4be06-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4be06-108">*HRESULT*</span></span>  
 <span data-ttu-id="4be06-109">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="4be06-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4be06-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="4be06-110">Return Value</span></span>  
 <span data-ttu-id="4be06-111">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="4be06-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4be06-112">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="4be06-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4be06-113">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="4be06-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4be06-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4be06-114">Requirements</span></span>  
 <span data-ttu-id="4be06-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4be06-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be06-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4be06-116">See Also</span></span>  
 [<span data-ttu-id="4be06-117">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4be06-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
