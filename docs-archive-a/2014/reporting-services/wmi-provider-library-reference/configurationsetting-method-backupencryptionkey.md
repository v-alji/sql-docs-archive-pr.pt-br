---
title: Método BackupEncryptionKey (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- BackupEncryptionKey Method (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- BackupEncryptionKey method
ms.assetid: da1d5dae-2517-448e-96fb-5379c93222ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d625401324e2117ee1e9677d840854fa7b63c6e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684010"
---
# <a name="backupencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d1790-102">Método BackupEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d1790-102">BackupEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d1790-103">Efetua backup da chave de criptografia da instância do servidor de relatório especificada.</span><span class="sxs-lookup"><span data-stu-id="d1790-103">Backs up the encryption key for the specified report server instance.</span></span> <span data-ttu-id="d1790-104">A chave de criptografia é armazenada criptografada com uma senha.</span><span class="sxs-lookup"><span data-stu-id="d1790-104">The encryption key is stored encrypted with a password.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1790-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1790-105">Syntax</span></span>  
  
```vb  
Public Sub BackupEncryptionKey(Password as String, _  
    ByRef KeyFile() as Integer, ByRef Length as Int32, _  
    ByRef HRESULT as Int32, ByRef ExtendedErrors() as String)  
  
```  
  
```csharp  
public void BackupEncryptionKey(string Password, out Byte[] KeyFile,   
    out Int32 Length, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1790-106">parâmetros</span><span class="sxs-lookup"><span data-stu-id="d1790-106">Parameters</span></span>  
 <span data-ttu-id="d1790-107">*Senha*</span><span class="sxs-lookup"><span data-stu-id="d1790-107">*Password*</span></span>  
 <span data-ttu-id="d1790-108">Uma cadeia de caracteres usada para criptografar a chave de criptografia antes de ela ser retornada.</span><span class="sxs-lookup"><span data-stu-id="d1790-108">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="d1790-109">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="d1790-109">*KeyFile[]*</span></span>  
 <span data-ttu-id="d1790-110">[fora] Uma matriz que contém a chave de criptografia criptografada.</span><span class="sxs-lookup"><span data-stu-id="d1790-110">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="d1790-111">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="d1790-111">*Length*</span></span>  
 <span data-ttu-id="d1790-112">[fora] O tamanho da matriz retornada pelo método.</span><span class="sxs-lookup"><span data-stu-id="d1790-112">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="d1790-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d1790-113">*HRESULT*</span></span>  
 <span data-ttu-id="d1790-114">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="d1790-114">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="d1790-115">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="d1790-115">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="d1790-116">[fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.</span><span class="sxs-lookup"><span data-stu-id="d1790-116">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1790-117">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="d1790-117">Return Value</span></span>  
 <span data-ttu-id="d1790-118">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="d1790-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d1790-119">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="d1790-119">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d1790-120">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="d1790-120">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1790-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1790-121">Requirements</span></span>  
 <span data-ttu-id="d1790-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1790-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1790-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1790-123">See Also</span></span>  
 [<span data-ttu-id="d1790-124">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d1790-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
