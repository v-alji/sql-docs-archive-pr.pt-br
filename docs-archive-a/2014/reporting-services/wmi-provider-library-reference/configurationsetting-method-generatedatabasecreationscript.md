---
title: Método GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572922"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="39591-102">Método GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="39591-102">GenerateDatabaseCreationScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="39591-103">Gera um SQL Script que pode ser usado para criar um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39591-103">Generates a SQL Script that can be used to create a report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39591-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="39591-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39591-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="39591-105">Parameters</span></span>  
 <span data-ttu-id="39591-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="39591-106">*Databasename*</span></span>  
 <span data-ttu-id="39591-107">Uma cadeia de caracteres que contém o nome do banco de dados do servidor de relatório a ser criado.</span><span class="sxs-lookup"><span data-stu-id="39591-107">A string containing the name of the report server database to create.</span></span>  
  
 <span data-ttu-id="39591-108">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="39591-108">*Lcid*</span></span>  
 <span data-ttu-id="39591-109">O valor usado para localização de nomes de função.</span><span class="sxs-lookup"><span data-stu-id="39591-109">Value used for localization of role names.</span></span>  
  
 <span data-ttu-id="39591-110">*IsSharePointMode*</span><span class="sxs-lookup"><span data-stu-id="39591-110">*IsSharePointMode*</span></span>  
 <span data-ttu-id="39591-111">Indica se o banco de dados deve ser criado no modo nativo ou no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39591-111">Indicates whether to create database in native mode or SharePoint mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39591-112">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , o *issharepointmode* = `True` não tem suporte porque, no modo do SharePoint, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é um serviço compartilhado do SharePoint e não é controlado pelo provedor WMI.</span><span class="sxs-lookup"><span data-stu-id="39591-112">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *IsSharePointMode*=`True` is not supported because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is a SharePoint shared service and is not controlled by the WMI provider.</span></span> <span data-ttu-id="39591-113">Você sempre deve definir esse parâmetro como `False`.</span><span class="sxs-lookup"><span data-stu-id="39591-113">You should always set this parameter to `False`.</span></span>  
  
 <span data-ttu-id="39591-114">*Script*</span><span class="sxs-lookup"><span data-stu-id="39591-114">*Script*</span></span>  
 <span data-ttu-id="39591-115">[fora] Uma cadeia de caracteres que contém o script SQL gerado.</span><span class="sxs-lookup"><span data-stu-id="39591-115">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="39591-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="39591-116">*HRESULT*</span></span>  
 <span data-ttu-id="39591-117">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="39591-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39591-118">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="39591-118">Return Value</span></span>  
 <span data-ttu-id="39591-119">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="39591-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="39591-120">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="39591-120">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="39591-121">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="39591-121">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39591-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="39591-122">Remarks</span></span>  
 <span data-ttu-id="39591-123">Este método gera um script SQL que cria bancos de dados de servidor de relatório para a versão do servidor de relatório à qual está conectado.</span><span class="sxs-lookup"><span data-stu-id="39591-123">This method generates an SQL script that creates report server databases for the version of the report server currently connected to.</span></span>  
  
 <span data-ttu-id="39591-124">O valor fornecido no parâmetro *DatabaseName* deve estar em conformidade com as convenções de nomenclatura de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39591-124">The value supplied in the *DatabaseName* parameter must conform to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database naming conventions.</span></span>  
  
 <span data-ttu-id="39591-125">O método não verifica se o banco de dados existe durante a geração do script.</span><span class="sxs-lookup"><span data-stu-id="39591-125">The method does not check the existence of the database when generating the script.</span></span>  
  
 <span data-ttu-id="39591-126">Este método não verifica se o banco de dados do servidor de relatório existe durante a geração do script.</span><span class="sxs-lookup"><span data-stu-id="39591-126">This method does not check for the existence of the report server database when generating the script.</span></span>  
  
 <span data-ttu-id="39591-127">O script gerado dá suporte ao [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 e ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39591-127">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39591-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39591-128">Requirements</span></span>  
 <span data-ttu-id="39591-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39591-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39591-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39591-130">See Also</span></span>  
 [<span data-ttu-id="39591-131">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="39591-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
