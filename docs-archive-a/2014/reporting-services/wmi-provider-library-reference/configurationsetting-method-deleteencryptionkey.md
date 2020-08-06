---
title: Método DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptionKey method
ms.assetid: ed2f25b6-6a63-468d-9279-a577ca01b096
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e302659615bd620b3b0ed802b83aafc4e9506d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572924"
---
# <a name="deleteencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="82c30-102">Método DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="82c30-102">DeleteEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="82c30-103">Exclui as chaves de criptografia do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="82c30-103">Deletes the encryption keys from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82c30-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82c30-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptionKeys(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptionKeys(string InstallationID, out Int32 HRESULT,   
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82c30-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="82c30-105">Parameters</span></span>  
 <span data-ttu-id="82c30-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="82c30-106">*InstallationID*</span></span>  
 <span data-ttu-id="82c30-107">A ID de instalação de um servidor de relatório que está na tabela de chaves do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="82c30-107">The installation ID of a report server that is in the keys table of the report server database.</span></span>  
  
 <span data-ttu-id="82c30-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="82c30-108">*HRESULT*</span></span>  
 <span data-ttu-id="82c30-109">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="82c30-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="82c30-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="82c30-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="82c30-111">[fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.</span><span class="sxs-lookup"><span data-stu-id="82c30-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82c30-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="82c30-112">Return Value</span></span>  
 <span data-ttu-id="82c30-113">Retorna um HRESULT indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="82c30-113">Returns an HRESULT indicating success or failure of the method call.</span></span> <span data-ttu-id="82c30-114">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="82c30-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="82c30-115">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="82c30-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82c30-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="82c30-116">Remarks</span></span>  
 <span data-ttu-id="82c30-117">O método *DeleteEncryptionKey* exclui entradas da tabela de chaves para qualquer servidor de relatório que tenha acesso a informações seguras do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="82c30-117">The *DeleteEncryptionKey* method deletes entries from the keys table for any report servers that have access to the secure information in the report server database.</span></span> <span data-ttu-id="82c30-118">Se o parâmetro *InstallationID* especificado não corresponder a uma ID de instalação do banco de dados, o método retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="82c30-118">If the *InstallationID* parameter specified does not correspond to an installation ID in the database, the method returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82c30-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82c30-119">Requirements</span></span>  
 <span data-ttu-id="82c30-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82c30-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c30-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82c30-121">See Also</span></span>  
 [<span data-ttu-id="82c30-122">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="82c30-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
