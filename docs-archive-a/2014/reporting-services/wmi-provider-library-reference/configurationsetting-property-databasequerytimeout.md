---
title: Propriedade DatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseQueryTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseQueryTimeout property
ms.assetid: 96faed97-9799-4bbf-a66f-fdd532d3eace
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e92e3e0f6752ea99fe89c962ebe96e343c0195b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683973"
---
# <a name="databasequerytimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b7c20-102">Propriedade DatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b7c20-102">DatabaseQueryTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b7c20-103">Especifica o número de segundos que devem decorrer antes de o servidor de relatório assumir que o comando falhou ou demorou demais para executar.</span><span class="sxs-lookup"><span data-stu-id="b7c20-103">Specifies the number of seconds that must elapse before the report server assumes the command failed or took too much time to perform.</span></span> <span data-ttu-id="b7c20-104">O servidor de relatório está cronometrando a consulta no catálogo de SQL, não uma fonte de dados para o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7c20-104">The report server is timing the querying against the SQL catalog, not a data source for the report.</span></span> <span data-ttu-id="b7c20-105">Leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="b7c20-105">Read/write.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c20-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b7c20-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseQueryTimeout As UInt32  
```  
  
```csharp  
public UInt32 DatabaseQueryTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="b7c20-107">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="b7c20-107">Property Values</span></span>  
 <span data-ttu-id="b7c20-108">Um objeto `integer` sem-sinal de 32 bits que representa o número de segundos que a consulta tem permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="b7c20-108">A 32-bit unsigned `integer` object that represents the number of seconds that the query is allowed to run.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="b7c20-109">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="b7c20-109">Example Code</span></span>  
 [<span data-ttu-id="b7c20-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b7c20-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="b7c20-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7c20-111">Requirements</span></span>  
 <span data-ttu-id="b7c20-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c20-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c20-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7c20-113">See Also</span></span>  
 [<span data-ttu-id="b7c20-114">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b7c20-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
