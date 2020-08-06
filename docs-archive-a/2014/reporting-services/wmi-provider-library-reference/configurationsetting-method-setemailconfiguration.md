---
title: Método SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEmailConfiguration method
ms.assetid: b40a2224-2c90-4d32-892f-1fe73a0591ca
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19068d7d7fff8c31c455ef76e8d2c2caa26b743f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683997"
---
# <a name="setemailconfiguration-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="8a255-102">Método SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="8a255-102">SetEmailConfiguration Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="8a255-103">Configura a extensão de entrega de email usada pelo servidor de relatório para enviar email.</span><span class="sxs-lookup"><span data-stu-id="8a255-103">Configures the e-mail delivery extension used by the report server to send e-mail.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a255-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8a255-104">Syntax</span></span>  
  
```vb  
Public Sub SetEmailConfiguration(ByVal SendUsingSMTPServer As Boolean, _  
    ByVal SMTPServer As String, ByVal SenderEmailAddress As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetEmailConfiguration (Boolean SendUsingSMTPServer,   
   string SMTPServer, string SenderEmailAddress,   
   out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a255-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="8a255-105">Parameters</span></span>  
 <span data-ttu-id="8a255-106">*SendUsingSMTPServer*</span><span class="sxs-lookup"><span data-stu-id="8a255-106">*SendUsingSMTPServer*</span></span>  
 <span data-ttu-id="8a255-107">Um valor Booleano que indica se o servidor deve usar o servidor SMTP para enviar email.</span><span class="sxs-lookup"><span data-stu-id="8a255-107">A Boolean value indicating whether the server is to use the SMTP server to send email.</span></span> <span data-ttu-id="8a255-108">Este valor só pode ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="8a255-108">This value can only be set to true.</span></span> <span data-ttu-id="8a255-109">O valor padrão é falso.</span><span class="sxs-lookup"><span data-stu-id="8a255-109">Default value is false.</span></span>  
  
 <span data-ttu-id="8a255-110">*SMTPServer*</span><span class="sxs-lookup"><span data-stu-id="8a255-110">*SMTPServer*</span></span>  
 <span data-ttu-id="8a255-111">Uma cadeia de caracteres que contém o nome ou o endereço IP de um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="8a255-111">A string containing the name or IP address of an SMTP server.</span></span>  
  
 <span data-ttu-id="8a255-112">*SenderEmailAddress*</span><span class="sxs-lookup"><span data-stu-id="8a255-112">*SenderEmailAddress*</span></span>  
 <span data-ttu-id="8a255-113">O endereço de email usado no campo 'De:' nos emails enviados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8a255-113">The e-mail address used in the 'From:' field for e-mails sent from the report server.</span></span>  
  
 <span data-ttu-id="8a255-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="8a255-114">*HRESULT*</span></span>  
 <span data-ttu-id="8a255-115">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="8a255-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a255-116">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="8a255-116">Return Value</span></span>  
 <span data-ttu-id="8a255-117">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="8a255-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="8a255-118">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="8a255-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="8a255-119">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="8a255-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a255-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="8a255-120">Remarks</span></span>  
 <span data-ttu-id="8a255-121">Quando o parâmetro *SendUsingSMTPServer* é definido como `true` , a entrada **SendUsing** no arquivo de configuração do servidor de relatório é definida como 1.</span><span class="sxs-lookup"><span data-stu-id="8a255-121">When the *SendUsingSMTPServer* parameter is set to `true`, the **SendUsing** entry in the report server configuration file is set to 1.</span></span> <span data-ttu-id="8a255-122">Quando *SendUsingSMTPServer* é definido como `false` , a entrada **SendUsing** não é configurada.</span><span class="sxs-lookup"><span data-stu-id="8a255-122">When *SendUsingSMTPServer* is set to `false`, the **SendUsing** entry is not configured.</span></span>  
  
 <span data-ttu-id="8a255-123">Esse método não fornece um modo de os usuários definirem a entrada **SendUsing** no arquivo de configuração do servidor de relatório para um valor diferente de 1.</span><span class="sxs-lookup"><span data-stu-id="8a255-123">This method does not provide a way for users to set the **SendUsing** entry in the report server configuration file to a value other than 1.</span></span> <span data-ttu-id="8a255-124">Para configurar o servidor de relatório para algo diferente de e-mail SMTP, você deverá editar o arquivo de configuração manualmente.</span><span class="sxs-lookup"><span data-stu-id="8a255-124">To configure the report server for anything other than SMTP mail, you must edit the configuration file manually.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a255-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a255-125">Requirements</span></span>  
 <span data-ttu-id="8a255-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a255-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a255-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a255-127">See Also</span></span>  
 [<span data-ttu-id="8a255-128">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8a255-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
