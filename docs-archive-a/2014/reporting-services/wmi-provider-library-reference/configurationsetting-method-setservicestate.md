---
title: Método SetServiceState (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683988"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a>Método SetServiceState (WMI MSReportServer_ConfigurationSetting)
  Ativa e desativa o Servidor de Relatório do Windows e os serviços Web.  
  
## <a name="syntax"></a>Sintaxe  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a>parâmetros  
 *EnableWindowsService*  
 Um valor `Boolean` que indica o estado do serviço do Windows. Um valor `true` inicia o serviço Servidor de Relatório do Windows; um valor `false` interrompe o serviço do Windows.  
  
 *EnableWebService*  
 Um `Boolean` valor que indica o estado do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] serviço Web. Um valor `true` inicia o serviço Web Servidor de Relatórios; um valor `false` interrompe o serviço Web.  
  
 *EnableReportManager*  
 Um valor `Boolean` que indica o estado desejado do Gerenciador de Relatórios.  
  
 *HRESULT*  
 [out] Valor que indica se a chamada obteve êxito ou falhou.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um *HRESULT* indicando êxito ou falha da chamada do método. Um valor 0 indica que a chamada do método teve êxito. Um valor diferente de zero indica que ocorreu um erro.  
  
## <a name="remarks"></a>Comentários  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
