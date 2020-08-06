---
title: Método SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetWindowsServiceIdentity method
ms.assetid: 9bbc734c-9e69-48c2-8bec-8abe7c6cc987
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15d1b7fa5fc6d69a963785cdaf976c80623c47f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683982"
---
# <a name="setwindowsserviceidentity-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="af709-102">Método SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="af709-102">SetWindowsServiceIdentity Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="af709-103">Faz com que o serviço do Windows do servidor de relatório seja executado como um usuário do Windows especificado e concede a esta conta permissões de sistema de arquivos suficientes para permitir que o servidor de relatório opere.</span><span class="sxs-lookup"><span data-stu-id="af709-103">Makes the Report Server Windows service run as a specified Windows user, and grants this account sufficient file system permissions to allow the report server to operate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af709-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="af709-104">Syntax</span></span>  
  
```vb  
Public Sub SetWindowsServiceIdentity(UseBuiltInAccount as Boolean, _  
    Account as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetWindowsServiceIdentity(boolean UseBuiltInAccount,   
    string Account, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af709-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="af709-105">Parameters</span></span>  
 <span data-ttu-id="af709-106">*UseBuiltInAccount*</span><span class="sxs-lookup"><span data-stu-id="af709-106">*UseBuiltInAccount*</span></span>  
 <span data-ttu-id="af709-107">Indica se a conta especificada é uma conta interna do Windows.</span><span class="sxs-lookup"><span data-stu-id="af709-107">Indicates whether the specified account is a built-in Windows account.</span></span>  
  
 <span data-ttu-id="af709-108">*Conta*</span><span class="sxs-lookup"><span data-stu-id="af709-108">*Account*</span></span>  
 <span data-ttu-id="af709-109">A conta do Windows a ser utilizada para executar o serviço de Windows, no formato "DOMAIN\alias".</span><span class="sxs-lookup"><span data-stu-id="af709-109">The Windows account to use to run the Windows service, in the format "DOMAIN\alias".</span></span>  
  
 <span data-ttu-id="af709-110">*Senha*</span><span class="sxs-lookup"><span data-stu-id="af709-110">*Password*</span></span>  
 <span data-ttu-id="af709-111">A senha para a conta.</span><span class="sxs-lookup"><span data-stu-id="af709-111">The password for the account.</span></span>  
  
 <span data-ttu-id="af709-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="af709-112">*HRESULT*</span></span>  
 <span data-ttu-id="af709-113">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="af709-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af709-114">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="af709-114">Return Value</span></span>  
 <span data-ttu-id="af709-115">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="af709-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="af709-116">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="af709-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="af709-117">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="af709-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af709-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="af709-118">Remarks</span></span>  
 <span data-ttu-id="af709-119">Quando o parâmetro *UseBuiltInAccount* é definido como `true` e o servidor de relatório é executado no Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] ou no Windows XP, o valor dos parâmetros *nome*, *domínio*e *senha* são ignorados e a conta sistema local é usada.</span><span class="sxs-lookup"><span data-stu-id="af709-119">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] or Windows XP, the value of the *Name*, *Domain*, and *Password* parameters are ignored and the Local system account is used.</span></span>  
  
 <span data-ttu-id="af709-120">Quando o parâmetro *UseBuiltInAccount* é definido como `true` e o servidor de relatório está em execução no Windows Server 2003, as propriedades de *domínio* e *senha* são ignoradas e o campo de nome deve conter "Builtin\NetworkService" ou "Builtin\System" ou "Builtin\LocalService".</span><span class="sxs-lookup"><span data-stu-id="af709-120">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Windows Server 2003, the *Domain* and *Password* properties are ignored, and the name field must contain either "Builtin\NetworkService" or "Builtin\System" or "Builtin\LocalService".</span></span>  
  
 <span data-ttu-id="af709-121">O método SetWindowsServiceIdentity define as permissões de arquivo nos arquivos e nas pastas do diretório de instalação do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="af709-121">The SetWindowsServiceIdentity method sets file permissions on files and folders in the report server installation directory.</span></span>  
  
 <span data-ttu-id="af709-122">A conta especificada no parâmetro de *conta* requer `LogonAsService` direitos no Windows.</span><span class="sxs-lookup"><span data-stu-id="af709-122">The account specified in the *Account* parameter requires `LogonAsService` rights in Windows.</span></span> <span data-ttu-id="af709-123">O método concede esse direito à conta especificada.</span><span class="sxs-lookup"><span data-stu-id="af709-123">The method grants this right to the specified account.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af709-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af709-124">Requirements</span></span>  
 <span data-ttu-id="af709-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af709-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af709-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af709-126">See Also</span></span>  
 [<span data-ttu-id="af709-127">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="af709-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
