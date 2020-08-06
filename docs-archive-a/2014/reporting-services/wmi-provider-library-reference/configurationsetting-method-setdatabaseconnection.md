---
title: Método SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseConnection method
ms.assetid: c040aa78-92b8-41e4-9ae2-eff9fcdddc5b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5c62777edd1fab2b0cb3babc13ab09f7bcf32a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684000"
---
# <a name="setdatabaseconnection-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="754e7-102">Método SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="754e7-102">SetDatabaseConnection Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="754e7-103">Define a conexão do banco de dados do servidor de relatório para um banco de dados do servidor de relatório específico.</span><span class="sxs-lookup"><span data-stu-id="754e7-103">Sets the report server database connection to a particular report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754e7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="754e7-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseConnection(Server as String, _  
    DatabaseName as string, CredentialsType as Integer, _  
    Username as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void BackupEncryptionKey(string Server,   
    string DatabaseName, Int32 CredentialsType,   
    string UserName, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="754e7-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="754e7-105">Parameters</span></span>  
 <span data-ttu-id="754e7-106">*Servidor*</span><span class="sxs-lookup"><span data-stu-id="754e7-106">*Server*</span></span>  
 <span data-ttu-id="754e7-107">O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado para hospedar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="754e7-107">The name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is used to host the report server database.</span></span>  
  
 <span data-ttu-id="754e7-108">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="754e7-108">*DatabaseName*</span></span>  
 <span data-ttu-id="754e7-109">O nome do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="754e7-109">The name of the report server database.</span></span>  
  
 <span data-ttu-id="754e7-110">*CredentialsType*</span><span class="sxs-lookup"><span data-stu-id="754e7-110">*CredentialsType*</span></span>  
 <span data-ttu-id="754e7-111">O tipo de credenciais a ser usada para a conexão.</span><span class="sxs-lookup"><span data-stu-id="754e7-111">The type of credentials to use for the connection.</span></span> <span data-ttu-id="754e7-112">Os valores podem ser:</span><span class="sxs-lookup"><span data-stu-id="754e7-112">Values can be:</span></span>  
  
-   <span data-ttu-id="754e7-113">0 - Windows</span><span class="sxs-lookup"><span data-stu-id="754e7-113">0 - Windows</span></span>  
  
-   <span data-ttu-id="754e7-114">1 – [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754e7-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="754e7-115">2 - Serviço do Windows</span><span class="sxs-lookup"><span data-stu-id="754e7-115">2 - Windows Service</span></span>  
  
 <span data-ttu-id="754e7-116">*UserName*</span><span class="sxs-lookup"><span data-stu-id="754e7-116">*UserName*</span></span>  
 <span data-ttu-id="754e7-117">O nome de conta usada para se conectar ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="754e7-117">The account name used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="754e7-118">*Senha*</span><span class="sxs-lookup"><span data-stu-id="754e7-118">*Password*</span></span>  
 <span data-ttu-id="754e7-119">A senha usada para se conectar ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="754e7-119">The password used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="754e7-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="754e7-120">*HRESULT*</span></span>  
 <span data-ttu-id="754e7-121">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="754e7-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="754e7-122">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="754e7-122">Return Value</span></span>  
 <span data-ttu-id="754e7-123">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="754e7-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="754e7-124">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="754e7-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="754e7-125">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="754e7-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="754e7-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="754e7-126">Remarks</span></span>  
 <span data-ttu-id="754e7-127">Quando o parâmetro *CredentialsType* for definido como 0 (Windows), os parâmetros *UserName* e *Password* devem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="754e7-127">When the *CredentialsType* parameter is set to 0 (Windows), the *UserName* and *Password* parameters must be set.</span></span> <span data-ttu-id="754e7-128">O parâmetro *UserName* deve estar no formulário "domain\username" e o valor deve representar um logon de Windows válido.</span><span class="sxs-lookup"><span data-stu-id="754e7-128">The *UserName* parameter must be in the form "domain\username", and the value must represent a valid Windows logon.</span></span>  
  
 <span data-ttu-id="754e7-129">Quando o parâmetro *CredentialsType* for definido como 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), o valor transmitido no parâmetro *UserName* deverá estar em conformidade com os requisitos de um nome de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="754e7-129">When the *CredentialsType* parameter is set to 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the value passed in the *UserName* parameter must conform to the requirements of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login name.</span></span>  
  
 <span data-ttu-id="754e7-130">Quando o parâmetro *CredentialsType* é definido como 2 (serviço Windows), o servidor de relatório usa a segurança integrada para se conectar ao banco de dados do servidor de relatório, e os parâmetros *UserName* e *Password* são ignorados.</span><span class="sxs-lookup"><span data-stu-id="754e7-130">When the *CredentialsType* parameter is set to 2 (Windows Service), the report server uses integrated security to connect to the report server database and the *UserName* and *Password* parameters are ignored.</span></span> <span data-ttu-id="754e7-131">O serviço Web Servidor de Relatórios usará a conta [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] ou uma conta do pool de aplicativos e a conta de serviço Windows para acessar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="754e7-131">The Reporting Server Web service will use either the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account or an application pool's account and the Windows service account to access the report server database.</span></span>  
  
 <span data-ttu-id="754e7-132">Quando chamado, o método SetDatabaseConnection criptografa e armazena as credenciais e informações do banco de dados no arquivo de configuração para o servidor de relatório especificado.</span><span class="sxs-lookup"><span data-stu-id="754e7-132">When called, the SetDatabaseConnection method encrypts and stores the credentials and database information in the configuration file for the specified report server.</span></span>  
  
 <span data-ttu-id="754e7-133">O método SetDatabaseConnection não verifica se o servidor de relatório pode se conectar ao banco de dados do servidor de relatório usando os dados especificados.</span><span class="sxs-lookup"><span data-stu-id="754e7-133">The SetDatabaseConnection method does not check that the report server can connect to the report server database using the data specified.</span></span>  
  
 <span data-ttu-id="754e7-134">Quando configurada pela primeira vez, a propriedade ConnectionPoolSize é definida com base nos seguintes processadores: ConnectionPoolSize = #Processadores \* 75.</span><span class="sxs-lookup"><span data-stu-id="754e7-134">When set for the first time, the ConnectionPoolSize property is set based on the following processors: ConnectionPoolSize = #Processors \* 75.</span></span>  
  
 <span data-ttu-id="754e7-135">O método SetDatabaseConnection não concede permissões para as contas especificadas.</span><span class="sxs-lookup"><span data-stu-id="754e7-135">The SetDatabaseConnection method does not grant permissions to the specified account(s).</span></span> <span data-ttu-id="754e7-136">Você deve chamar o método [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) para cada conta que requer acesso ao banco de dados do servidor de relatório e executar o script resultante.</span><span class="sxs-lookup"><span data-stu-id="754e7-136">You must call the [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) method for each account that requires access to the report server database and run the resulting script.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="754e7-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="754e7-137">Requirements</span></span>  
 <span data-ttu-id="754e7-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754e7-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754e7-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="754e7-139">See Also</span></span>  
 [<span data-ttu-id="754e7-140">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="754e7-140">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
