---
title: Método RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveUnattendedExecutionAccount method
ms.assetid: 77e371c1-7c26-44f9-9119-7c8dc838db32
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efe0523c9aa13315399c043367ef05a63da46e91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682075"
---
# <a name="removeunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="81945-102">Método RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="81945-102">RemoveUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="81945-103">Exclui a entrada de conta de execução autônoma do arquivo de configuração do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="81945-103">Deletes the unattended execution account entry from the report server configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81945-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="81945-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveUnattendedExecutionAccount(ByRef HRESULT as Int32)  
```  
  
```csharp  
public void RemoveUnattendedExecutionAccount (out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81945-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="81945-105">Parameters</span></span>  
 <span data-ttu-id="81945-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="81945-106">*HRESULT*</span></span>  
 <span data-ttu-id="81945-107">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="81945-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81945-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="81945-108">Return Value</span></span>  
 <span data-ttu-id="81945-109">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="81945-109">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="81945-110">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="81945-110">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="81945-111">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="81945-111">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81945-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81945-112">Requirements</span></span>  
 <span data-ttu-id="81945-113">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81945-113">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81945-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81945-114">See Also</span></span>  
 [<span data-ttu-id="81945-115">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="81945-115">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  