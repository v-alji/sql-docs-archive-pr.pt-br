---
title: Método SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetUnattendedExecutionAccount method
ms.assetid: 1ba6be6f-b05c-4ea0-af98-cd0780290b70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 73cf4c633c51de1e3e6b878c66d73ee710e98df6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683990"
---
# <a name="setunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="00493-102">Método SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="00493-102">SetUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="00493-103">Especifica a conta usada para executar relatórios autônomos.</span><span class="sxs-lookup"><span data-stu-id="00493-103">Specifies the account used to execute reports unattended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00493-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="00493-104">Syntax</span></span>  
  
```vb  
Public Sub SetUnattendedExecutionAccount(UserName as String, _  
    Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetUnattendedExecutionAccount (string UserName,   
    string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00493-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="00493-105">Parameters</span></span>  
 <span data-ttu-id="00493-106">*UserName*</span><span class="sxs-lookup"><span data-stu-id="00493-106">*UserName*</span></span>  
 <span data-ttu-id="00493-107">Uma conta do Windows a ser usada para execuções autônomas.</span><span class="sxs-lookup"><span data-stu-id="00493-107">A Windows account to be used for unattended executions.</span></span>  
  
 <span data-ttu-id="00493-108">*Senha*</span><span class="sxs-lookup"><span data-stu-id="00493-108">*Password*</span></span>  
 <span data-ttu-id="00493-109">A senha da conta especificada.</span><span class="sxs-lookup"><span data-stu-id="00493-109">The password for the specified account.</span></span>  
  
 <span data-ttu-id="00493-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="00493-110">*HRESULT*</span></span>  
 <span data-ttu-id="00493-111">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="00493-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00493-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="00493-112">Return Value</span></span>  
 <span data-ttu-id="00493-113">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="00493-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="00493-114">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="00493-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="00493-115">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="00493-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00493-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="00493-116">Remarks</span></span>  
 <span data-ttu-id="00493-117">O método SetUnattendedExecutionAccount não verifica se o servidor de relatório pode fazer o logon como o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="00493-117">The SetUnattendedExecutionAccount method does not verify whether the report server can log in as the specified user.</span></span>  
  
 <span data-ttu-id="00493-118">Não é possível usar o método SetUnattendedExecutionAccount para execuções autônomas no contexto do serviço Windows do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="00493-118">It is not possible to use the SetUnattendedExecutionAccount method to run unattended executions in the context of the report server Windows service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00493-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00493-119">Requirements</span></span>  
 <span data-ttu-id="00493-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00493-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00493-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00493-121">See Also</span></span>  
 [<span data-ttu-id="00493-122">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="00493-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
