# Changelog

## Unreleased

* Removes .NET Framework 4.5.2 support. The minimum .NET Framework version
  supported is .NET 4.6.1. ([#2138](https://github.com/open-telemetry/opentelemetry-dotnet/issues/2138))

## 1.1.0

Released 2021-Jul-12

## 1.1.0-rc1

Released 2021-Jun-25

## 1.1.0-beta4

Released 2021-Jun-09

## 1.1.0-beta3

Released 2021-May-11

## 1.1.0-beta2

Released 2021-Apr-23

* When using OpenTelemetry.Extensions.Hosting you can now bind
  `ZipkinExporterOptions` to `IConfiguration` using the `Configure` extension
  (ex:
  `services.Configure<ZipkinExporterOptions>(this.Configuration.GetSection("Zipkin"));`).
  ([#1889](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1889))

## 1.1.0-beta1

Released 2021-Mar-19

## 1.0.1

Released 2021-Feb-10

## 1.0.0-rc4

Released 2021-Feb-09

## 1.0.0-rc3

Released 2021-Feb-04

* Moved `ZipkinExporter` and `ZipkinExporterOptions` classes to
  `OpenTelemetry.Exporter` namespace.
  ([#1770](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1770))
* Removes ability to configure ServiceName for Zipkin. ServiceName must come
  via Resource. If service name is not found in Resource, Zipkin uses
  GetDefaultResource() from the SDK to obtain it.
  [#1768](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1768)

## 1.0.0-rc2

Released 2021-Jan-29

* Changed `ZipkinExporter` class and constructor from internal to public.
  ([#1612](https://github.com/open-telemetry/opentelemetry-dotnet/issues/1612))

* Zipkin will now set the `error` tag to the `Status.Description` value or an
  empty string when `Status.StatusCode` (`otel.status_code` tag) is set to
  `ERROR`.
  ([#1579](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1579),
  [#1620](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1620), &
  [#1655](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1655))

* Zipkin will no longer send the `otel.status_code` tag if the value is `UNSET`.
  ([#1609](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1609) &
  [#1620](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1620))

* Zipkin bool tag values will now be sent as `true`/`false` instead of
  `True`/`False`.
  ([#1609](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1609))

* Span tags will no longer be populated with Resource Attributes.
  ([#1663](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1663))

* Spans will no longer be held in memory indefinitely when `ZipkinExporter`
  cannot connect to the configured endpoint.
  ([#1726](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1726))

## 1.0.0-rc1.1

Released 2020-Nov-17

* Added ExportProcessorType to exporter options
  ([#1504](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1504))
* Zipkin tags used for InstrumentationLibrary changed from library.name,
  library.version to otel.library.name, otel.library.version respectively.
* Sending `service.namespace` as Zipkin tag.
  ([#1521](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1521))
* The `ZipkinExporter` class has been made internal.
  ([#1540](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1540))

## 0.8.0-beta.1

Released 2020-Nov-5

* ZipkinExporter will now respect global Resource set via
  `TracerProviderBuilder.SetResource`.
  ([#1385](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1385))

## 0.7.0-beta.1

Released 2020-Oct-16

* Removed unused `TimeoutSeconds` and added `MaxPayloadSizeInBytes` on
  `ZipkinExporterOptions`. The default value for `MaxPayloadSizeInBytes` is
  4096.
  ([#1247](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1274))

## 0.6.0-beta.1

Released 2020-Sep-15

## 0.5.0-beta.2

Released 2020-08-28

* Renamed extension method from `UseZipkinExporter` to `AddZipkinExporter`
  ([#1066](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1066))
* Changed `ZipkinExporter` to use `BatchExportActivityProcessor` by default
  ([#1103](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1103))
* Fixed issue when span has both the `net.peer.name` and `net.peer.port`
  attributes but did not include `net.peer.port` in the service address field
  ([#1168](https://github.com/open-telemetry/opentelemetry-dotnet/pull/1168)).

## 0.4.0-beta.2

Released 2020-07-24

* First beta release

## 0.3.0-beta

Released 2020-07-23

* Initial release
