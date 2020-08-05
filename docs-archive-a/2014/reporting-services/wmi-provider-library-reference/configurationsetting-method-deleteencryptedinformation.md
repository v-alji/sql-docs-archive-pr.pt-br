---
title: Método DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptedInformation method
ms.assetid: c14ed187-bdd9-4304-88e3-72072f03c21b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d00dc3e90816cd04c84f124cdc3d25a9ac122bba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572931"
---
# <a name="deleteencryptedinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="51b4f-102">Método DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="51b4f-102">DeleteEncryptedInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="51b4f-103">Exclui as informações criptografadas do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="51b4f-103">Deletes the encrypted information from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b4f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="51b4f-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptedInformation(ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptedInformation(out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51b4f-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="51b4f-105">Parameters</span></span>  
 <span data-ttu-id="51b4f-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="51b4f-106">*HRESULT*</span></span>  
 <span data-ttu-id="51b4f-107">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="51b4f-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="51b4f-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="51b4f-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="51b4f-109">[fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.</span><span class="sxs-lookup"><span data-stu-id="51b4f-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51b4f-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="51b4f-110">Return Value</span></span>  
 <span data-ttu-id="51b4f-111">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="51b4f-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="51b4f-112">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="51b4f-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="51b4f-113">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="51b4f-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51b4f-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="51b4f-114">Remarks</span></span>  
 <span data-ttu-id="51b4f-115">Quando esse método é chamado, os dados a seguir são excluídos:</span><span class="sxs-lookup"><span data-stu-id="51b4f-115">When this method is invoked, the following data is deleted:</span></span>  
  
-   <span data-ttu-id="51b4f-116">As informações da origem de dados que são criptografadas, inclusive nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="51b4f-116">Data source information that is encrypted, including user name and password.</span></span>  
  
-   <span data-ttu-id="51b4f-117">Os dados da assinatura que são criptografados por meio das interfaces de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="51b4f-117">Subscription data that is encrypted using the delivery extension interfaces.</span></span>  
  
-   <span data-ttu-id="51b4f-118">Todas as informações da tabela de chaves no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="51b4f-118">All the information from the keys table in the report server database.</span></span>  
  
 <span data-ttu-id="51b4f-119">Depois que esse método é chamado, o usuário deve inicializar cada computador que usa o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="51b4f-119">After this method is invoked, the user must initialize each computer that uses the report server database.</span></span>  
  
 <span data-ttu-id="51b4f-120">Chamar o método DeleteEncryptedInformation não afeta o arquivo de configuração do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="51b4f-120">Calling the DeleteEncryptedInformation method does not affect the report server configuration file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51b4f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51b4f-121">Requirements</span></span>  
 <span data-ttu-id="51b4f-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51b4f-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b4f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51b4f-123">See Also</span></span>  
 [<span data-ttu-id="51b4f-124">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="51b4f-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
