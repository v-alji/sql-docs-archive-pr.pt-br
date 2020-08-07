---
title: Método ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576204"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d32ba-102">Método ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d32ba-102">ReencryptSecureInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d32ba-103">Gera uma nova chave de criptografia e criptografa novamente todas as informações seguras no catálogo usando essa nova chave.</span><span class="sxs-lookup"><span data-stu-id="d32ba-103">Generates a new encryption key and re-encrypts all secure information in the catalog using this new key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d32ba-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d32ba-104">Syntax</span></span>  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d32ba-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="d32ba-105">Parameters</span></span>  
 <span data-ttu-id="d32ba-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d32ba-106">*HRESULT*</span></span>  
 <span data-ttu-id="d32ba-107">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="d32ba-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="d32ba-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="d32ba-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="d32ba-109">[fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.</span><span class="sxs-lookup"><span data-stu-id="d32ba-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d32ba-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="d32ba-110">Return Value</span></span>  
 <span data-ttu-id="d32ba-111">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="d32ba-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d32ba-112">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="d32ba-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d32ba-113">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="d32ba-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d32ba-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="d32ba-114">Remarks</span></span>  
 <span data-ttu-id="d32ba-115">O método ReencryptSecureInformation permite que o administrador substitua a chave de criptografia existente com uma chave nova.</span><span class="sxs-lookup"><span data-stu-id="d32ba-115">The ReencryptSecureInformation method allows the administrator to replace the existing encryption key with a new key.</span></span>  
  
 <span data-ttu-id="d32ba-116">Quando esse método é chamado, o servidor de relatório gera uma nova chave de criptografia e itera por meio de todo o conteúdo criptografado para criptografá-lo novamente com a nova chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="d32ba-116">When this method is invoked, the report server generates a new encryption key and iterates through all encrypted content to re-encrypt it with the new encryption key.</span></span>  
  
 <span data-ttu-id="d32ba-117">As extensões de entrega podem armazenar informações seguras em suas estruturas de configurações de entrega.</span><span class="sxs-lookup"><span data-stu-id="d32ba-117">Delivery extensions can store secured information in their delivery settings structures.</span></span> <span data-ttu-id="d32ba-118">Quando o ReencryptSecureInformation é chamado, o servidor de relatório carrega cada assinatura e a extensão de entrega correspondente para criptografar novamente as informações armazenadas nas configurações associadas.</span><span class="sxs-lookup"><span data-stu-id="d32ba-118">When ReencryptSecureInformation is called, the report server loads each subscription and the corresponding delivery extension to re-encrypt information stored in the associated settings.</span></span>  
  
 <span data-ttu-id="d32ba-119">Se esse método for executado em um computador em uma implantação de expansão, cada computador na implantação de expansão precisará ser inicializado novamente.</span><span class="sxs-lookup"><span data-stu-id="d32ba-119">If this method is run on a computer in a scale-out deployment, each computer in the scale-out deployment will need to be initialized again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d32ba-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d32ba-120">Requirements</span></span>  
 <span data-ttu-id="d32ba-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d32ba-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32ba-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d32ba-122">See Also</span></span>  
 [<span data-ttu-id="d32ba-123">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d32ba-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
