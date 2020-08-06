---
title: Método SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseLogonTimeout method
ms.assetid: b8773596-5b98-4355-a4ab-4412e1317c67
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf93cd9158c3489db611446ac8523701f52831f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683999"
---
# <a name="setdatabaselogontimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="7182b-102">Método SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="7182b-102">SetDatabaseLogonTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="7182b-103">Especifica o valor de tempo limite padrão para as conexões do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7182b-103">Specifies the default timeout value for report server database connections.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7182b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7182b-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseLogonTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseLogonTimeout(Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7182b-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="7182b-105">Parameters</span></span>  
 <span data-ttu-id="7182b-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="7182b-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="7182b-107">O valor de tempo limite padrão, em segundos, para as conexões do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7182b-107">The default time-out value, in seconds, for report server database connections.</span></span>  
  
 <span data-ttu-id="7182b-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="7182b-108">*HRESULT*</span></span>  
 <span data-ttu-id="7182b-109">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="7182b-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7182b-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="7182b-110">Return Value</span></span>  
 <span data-ttu-id="7182b-111">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="7182b-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="7182b-112">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="7182b-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="7182b-113">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="7182b-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7182b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7182b-114">Requirements</span></span>  
 <span data-ttu-id="7182b-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7182b-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7182b-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7182b-116">See Also</span></span>  
 [<span data-ttu-id="7182b-117">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7182b-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
