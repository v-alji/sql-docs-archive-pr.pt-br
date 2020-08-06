---
title: Método SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683995"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a>Método SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)
  Especifica o valor de tempo limite padrão para consultas no banco de dados do servidor de relatório.  
  
## <a name="syntax"></a>Sintaxe  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a>parâmetros  
 *LogonTimeout*  
 O valor de tempo limite padrão, em segundos, para as consultas do banco de dados do servidor de relatório.  
  
 *HRESULT*  
 [out] Valor que indica se a chamada obteve êxito ou falhou.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um *HRESULT* indicando êxito ou falha da chamada do método. Um valor 0 indica que a chamada do método teve êxito. Um valor diferente de zero indica que ocorreu um erro.  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
