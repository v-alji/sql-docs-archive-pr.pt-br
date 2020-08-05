---
title: Método CreateSSLCertificateBinding (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CreateSSLCertificateBinding
ms.assetid: 407d50e4-0a55-43cb-8ddf-2d82714071b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b9a5f9394d655f7b0592ea688a46f3ac2b9c153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572933"
---
# <a name="createsslcertificatebinding-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6f29c-102">Método CreateSSLCertificateBinding (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6f29c-102">CreateSSLCertificateBinding Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6f29c-103">Cria uma associação de Certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="6f29c-103">Creates an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f29c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6f29c-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void CreateSSLCertificateBinding(string application,   
    string certificateHash, string IPAddress, int Port,   
    int lcid, out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f29c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6f29c-105">Parameters</span></span>  
 <span data-ttu-id="6f29c-106">*Aplicativo*</span><span class="sxs-lookup"><span data-stu-id="6f29c-106">*Application*</span></span>  
 <span data-ttu-id="6f29c-107">O nome do aplicativo para o qual a associação de certificado deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="6f29c-107">The name of application that the certificate binding should be created for.</span></span>  
  
 <span data-ttu-id="6f29c-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="6f29c-108">*CertificateHash*</span></span>  
 <span data-ttu-id="6f29c-109">O hash para o certificado.</span><span class="sxs-lookup"><span data-stu-id="6f29c-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="6f29c-110">*EndereçoIP*</span><span class="sxs-lookup"><span data-stu-id="6f29c-110">*IPAddress*</span></span>  
 <span data-ttu-id="6f29c-111">O endereço IP para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6f29c-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="6f29c-112">*Porta*</span><span class="sxs-lookup"><span data-stu-id="6f29c-112">*Port*</span></span>  
 <span data-ttu-id="6f29c-113">A porta SSL relacionada à associação.</span><span class="sxs-lookup"><span data-stu-id="6f29c-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="6f29c-114">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="6f29c-114">*Lcid*</span></span>  
 <span data-ttu-id="6f29c-115">A localidade a ser usada para as mensagens de erro retornadas.</span><span class="sxs-lookup"><span data-stu-id="6f29c-115">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="6f29c-116">*Erro*</span><span class="sxs-lookup"><span data-stu-id="6f29c-116">*Error*</span></span>  
 <span data-ttu-id="6f29c-117">[fora] A descrição dos erros ocorridos.</span><span class="sxs-lookup"><span data-stu-id="6f29c-117">[out] The description of the errors that occurred.</span></span>  
  
 <span data-ttu-id="6f29c-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6f29c-118">*HRESULT*</span></span>  
 <span data-ttu-id="6f29c-119">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="6f29c-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f29c-120">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6f29c-120">Return Value</span></span>  
 <span data-ttu-id="6f29c-121">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="6f29c-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6f29c-122">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6f29c-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f29c-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="6f29c-123">Remarks</span></span>  
 <span data-ttu-id="6f29c-124">Este método adiciona uma associação a rsreportserver.config para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6f29c-124">This method adds a binding to rsreportserver.config for the application.</span></span> <span data-ttu-id="6f29c-125">Caso ainda não exista uma associação em HTTP.SYS, ela será criada ali.</span><span class="sxs-lookup"><span data-stu-id="6f29c-125">If a binding does not already exist in HTTP.SYS, it is created there.</span></span>  
  
 <span data-ttu-id="6f29c-126">Antes de criar a associação, a chamada do método examina as Reservas de Url referentes ao aplicativo especificado a fim de determinar se a Associação de Certificado SSL é válida.</span><span class="sxs-lookup"><span data-stu-id="6f29c-126">Before creating the binding, the method call examines the Url Reservations for the specified application to determine if the SSL Certificate Binding is valid.</span></span>  
  
 <span data-ttu-id="6f29c-127">As seguintes condições são validadas e podem resultar em erros:</span><span class="sxs-lookup"><span data-stu-id="6f29c-127">The following conditions are validated and can result in errors:</span></span>  
  
1.  <span data-ttu-id="6f29c-128">O certificado não existe.</span><span class="sxs-lookup"><span data-stu-id="6f29c-128">Certificate does not exist.</span></span>  
  
2.  <span data-ttu-id="6f29c-129">O valor IPAddress especificado não corresponde a um IPAddress deste computador.</span><span class="sxs-lookup"><span data-stu-id="6f29c-129">The IPAddress specified does not correspond to an IPAddress of this computer.</span></span>  
  
3.  <span data-ttu-id="6f29c-130">O IPAddress especificado é um IPAddress DHCP (muda periodicamente) – no lugar dele, use o endereço IP curinga (0.0.0.0).</span><span class="sxs-lookup"><span data-stu-id="6f29c-130">The IPAddress specified is a DHCP IPAddress (changes periodically) - use the Wildcard IP address instead (0.0.0.0).</span></span>  
  
4.  <span data-ttu-id="6f29c-131">O IPAddress especificado não corresponde ao endereço IP de uma reserva de URL, tampouco existe uma reserva de URL com nome de host ou curinga.</span><span class="sxs-lookup"><span data-stu-id="6f29c-131">IPAddress specified does not match the IP address of a URL reservations AND neither a wildcard or host name URL reservation exist.</span></span>  
  
5.  <span data-ttu-id="6f29c-132">Uma reserva de URL que especifica que existe um nome de host, mas o nome de host não corresponde ao nome de host do certificado.</span><span class="sxs-lookup"><span data-stu-id="6f29c-132">A URL reservation that specifies a host name exists, but the host name does not match the certificate host name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f29c-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f29c-133">Requirements</span></span>  
 <span data-ttu-id="6f29c-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f29c-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f29c-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f29c-135">See Also</span></span>  
 [<span data-ttu-id="6f29c-136">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6f29c-136">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
