---
title: Método InitializeReportServer (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- InitializeReportServer (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- InitializeReportServer method
ms.assetid: 0304acc2-1fd7-437b-94d9-1c1073dd3ca4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6a8e44a98320ca2c9add6a1b6eef9362eef7731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572920"
---
# <a name="initializereportserver-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="5522b-102">Método InitializeReportServer (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="5522b-102">InitializeReportServer Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="5522b-103">Inicializa a instância do serviço de relatório especificada.</span><span class="sxs-lookup"><span data-stu-id="5522b-103">Initializes the specified report service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5522b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5522b-104">Syntax</span></span>  
  
```vb  
Public Sub InitializeReportServer(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void InitializeReportServer(string InstallationID,   
    out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5522b-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="5522b-105">Parameters</span></span>  
 <span data-ttu-id="5522b-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="5522b-106">*InstallationID*</span></span>  
 <span data-ttu-id="5522b-107">Uma cadeia de caracteres usada para criptografar a chave de criptografia antes de ela ser retornada.</span><span class="sxs-lookup"><span data-stu-id="5522b-107">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="5522b-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="5522b-108">*HRESULT*</span></span>  
 <span data-ttu-id="5522b-109">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="5522b-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="5522b-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="5522b-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="5522b-111">[fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.</span><span class="sxs-lookup"><span data-stu-id="5522b-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5522b-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="5522b-112">Return Value</span></span>  
 <span data-ttu-id="5522b-113">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="5522b-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="5522b-114">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="5522b-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="5522b-115">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="5522b-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5522b-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="5522b-116">Remarks</span></span>  
 <span data-ttu-id="5522b-117">Quando este método é chamado, a chave de criptografia que acessa as informações seguras do banco de dados do servidor de relatório é criptografada usando-se a chave pública do servidor de relatório identificada por *InstallationID*.</span><span class="sxs-lookup"><span data-stu-id="5522b-117">When this method is called, the encryption key that accesses the report server database secure information is encrypted using the public key of the report server identified by *InstallationID*.</span></span>  
  
 <span data-ttu-id="5522b-118">A chave pública do servidor de relatório especificada deve ter sido gravada previamente no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5522b-118">The specified report server's public key must have previously been written into the report server database.</span></span>  
  
 <span data-ttu-id="5522b-119">O método *InitializeReportServer* deve ser chamado em um servidor de relatório que já tenha acesso às informações seguras para que possa descriptografar a chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="5522b-119">The *InitializeReportServer* method must be called against a report server that already has access to the secure information so that it can decrypt the encryption key.</span></span> <span data-ttu-id="5522b-120">Em seguida, a chave de criptografia criptografada resultante é armazenada no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5522b-120">The resulting encrypted encryption key is then stored in the report server database.</span></span>  
  
 <span data-ttu-id="5522b-121">Se a propriedade [IsInitialized](configurationsetting-property-isinitialized.md) do servidor de relatório for definida como `true` quando o método InitializeReportServer for chamado, o método retornará êxito sem tentar criptografar a chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="5522b-121">If the report server's [IsInitialized](configurationsetting-property-isinitialized.md) property is set to `true` when the InitializeReportServer method is called, the method returns success without trying to encrypt the encryption key.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5522b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5522b-122">Requirements</span></span>  
 <span data-ttu-id="5522b-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5522b-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5522b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5522b-124">See Also</span></span>  
 [<span data-ttu-id="5522b-125">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="5522b-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
