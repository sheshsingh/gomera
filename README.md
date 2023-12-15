# **Swat Gesinen**

This project is the client side of a management platform to control different IoT devices used to measure the consumption of water, electricity and other basic products installed in towns, houses, etc.

# **Contents**

- [**Swat Gesinen**](#swat-gesinen)
- [**Contents**](#contents)
- [**Pre requirements**](#pre-requirements)
- [**Getting started**](#getting-started)
- [**Project structure**](#project-structure)
- [**Network management**](#network-management)
  - [**Network server**](#network-server)
  - [**Gateways**](#gateways)
  - [**Sensors**](#sensors)
  - [**Projects**](#projects)
  - [**Users**](#users)
- [**Modules**](#modules)
  - [**Water module**](#water-module)
    - [**General**](#general)
    - [**Water devices**](#water-devices)
    - [**Water users**](#water-users)
- [**Deployment**](#deployment)
- [**License**](#license)

# **Pre requirements**

This project is being developed using `Angular 8` so you need to be installed this framework and the other packages needed to run Angular in your computer.

- Install [Node.js](https://nodejs.org/es/) (Max supported version is latest 14.x.x)
- Install [npm](https://www.npmjs.com/)
- Install [Angular](https://angular.io/)

# **Getting started**

1. Clone the repository

```
git clone https://github.com/sheshsingh/swat_gesinen
```

2. Install node modules

```
cd swat_gesinen
npm install
```

3. Run server

```
ng serve --open
```

Now, you can navigate to `http:\\localhost:4200` to see the project running in your browser.

> If your port 4200 is bussy, you can change it using the command `ng serve --p <port>`

# **Project structure**

```
package-lock.json
package.json
src/
	├── app/
    │   ├── views/
    │   │   ├── alarms/
    │   │   │   ├── define-sensor-alarms/
    │   │   │   │   ├── define-sensor.component.html
    │   │   │   │   ├── define-sensor.component.scss
    │   │   │   │   └── define-sensor.component.ts
    │   │   │   │
    │   │   │   ├── sensor-alarms/
    │   │   │   │   ├── sensor-alarms.component.html
    │   │   │   │   ├── sensor-alarms.component.scss
    │   │   │   │   └── sensor-alarms.component.ts
    │   │   │   │
    │   │   │   ├── sensor-alarms-notification/
    │   │   │   │   └── sensor-alarms-notification.component...
    │   │   │   │
    │   │   │   ├── alarms.module.ts
    │   │   │   ├── alarms.routing.ts
    │   │   │   └── alarms.service.ts
    │   │   │
    │   │   ├── dashboard/
    │   │   │   ├── default-dashboard/
    │   │   │   │   └── default-dashboard.component...
    │   │   │   │
    │   │   │   ├── dashboard.module.ts
    │   │   │   ├── dashboard.routing.ts
    │   │   │   └── dashboard.service.ts
    │   │   │
    │   │   ├── doormanagement/
    │   │   │   ├── calendar/
    │   │   │   │   ├── calendar-form-dialog/
    │   │   │   │   │   └── calendar-form.component...
    │   │   │   │   │
    │   │   │   │   ├── calendar.component...
    │   │   │   │   ├── calendar.module.ts
    │   │   │   │   ├── calendar.routing.ts
    │   │   │   │   └── calendar.service.ts
    │   │   │   │
    │   │   │   ├── door/
    │   │   │   │   ├── door-popup/
    │   │   │   │   │   ├── door-popup.component.html
    │   │   │   │   │   └── door-popup.service.ts
    │   │   │   │   │
    │   │   │   │   ├── door.component.html
    │   │   │   │   ├── door.component.scss
    │   │   │   │   ├── door.component.ts
    │   │   │   │   └── door.service.ts
    │   │   │   │
    │   │   │   │
    │   │   │   ├── doorhistory/
    │   │   │   │   └── doorhistory.component...
    │   │   │   │
    │   │   │   │
    │   │   │   ├── requests/
    │   │   │   │   ├── requests.component...
    │   │   │   │   └── requests.service.ts
    │   │   │   │
    │   │   │   │
    │   │   │   ├── users/
    │   │   │   │   ├── user-popup/
    │   │   │   │   │   ├── user-popup.component.html
    │   │   │   │   │   └── user-popup.service.ts
    │   │   │   │   │
    │   │   │   │   ├── users.component...
    │   │   │   │   ├── users-resolver.service.ts
    │   │   │   │   └── user.service.ts
    │   │   │   │
    │   │   │   │
    │   │   │   ├── constents.ts
    │   │   │   ├── door-status.pipe.ts
    │   │   │   ├── door.service.ts
    │   │   │   ├── doormanagement.module.ts
    │   │   │   ├── http-interceptor.service.ts
    │   │   │   ├── pagination.ts
    │   │   │   └── snackbar.service.ts
    │   │   │
    │   │   ├── energy-management/
    │   │   │   ├── actuator/
    │   │   │   │   ├── actuator.component...
    │   │   │   │   └── actuator.module.ts
    │   │   │   │
    │   │   │   ├── alarm/
    │   │   │   │   ├── alarm-list/
    │   │   │   │   │   └── alarm-list.component...
    │   │   │   │   │
    │   │   │   │   ├── define-alarm/
    │   │   │   │   │   ├── actuator.component.html
    │   │   │   │   │   └── actuator.module.ts
    │   │   │   │   │
    │   │   │   │   ├── alarm.component...
    │   │   │   │   └── alarm.module.ts
    │   │   │   │
    │   │   │   ├── contorl-cabinet/
    │   │   │   │   ├── control-cabinet.component...
    │   │   │   │   └── control-cabinet.module.ts
    │   │   │   │
    │   │   │   ├── dashboard/
    │   │   │   │   ├── dashboard.component...
    │   │   │   │   ├── dashboard.module.ts
    │   │   │   │   └── dashboard.service.ts
    │   │   │   │
    │   │   │   ├── energy-group-listing/
    │   │   │   │   ├── energy-group-listing.component...
    │   │   │   │   └── energy-group-listing.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-add/
    │   │   │   │   ├── energy-management-add.component...
    │   │   │   │   └── energy-management-add.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-input-add/
    │   │   │   │   ├── energy-management-input-add.component...
    │   │   │   │   └── energy-management-input-add.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-input-listing/
    │   │   │   │   ├── energy-management-input-listing.component...
    │   │   │   │   └── energy-management-input-listing.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-listing/
    │   │   │   │   ├── energy-management-listing.component...
    │   │   │   │   └── energy-management-listing.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-output-add/
    │   │   │   │   ├── energy-management-output-add.component...
    │   │   │   │   └── energy-management-output-add.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-output-input-status/
    │   │   │   │   ├── energy-management-output-input-status.component...
    │   │   │   │   └── energy-management-output-input-status.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-output-listing/
    │   │   │   │   ├── energy-management-output-listing.component...
    │   │   │   │   └── energy-management-output-listing.module.ts
    │   │   │   │
    │   │   │   ├── energy-management-view/
    │   │   │   │   ├── energy-management-view.component...
    │   │   │   │   └── energy-management-view.module.ts
    │   │   │   │
    │   │   │   ├── group-add/
    │   │   │   │   ├── group-add.component...
    │   │   │   │   └── group-add.module.ts
    │   │   │   │
    │   │   │   ├── history/
    │   │   │   │   ├── history.component...
    │   │   │   │   └── history.module.ts
    │   │   │   │
    │   │   │   ├── planning/
    │   │   │   │   ├── planning-copy-popup/
    │   │   │   │   │   └── planning-copy-popup.component...
    │   │   │   │   │
    │   │   │   │   ├── planning-day/
    │   │   │   │   │   └── planning-day.component...
    │   │   │   │   │
    │   │   │   │   ├── planning-day-popup-list/
    │   │   │   │   │   └── planning-day.component...
    │   │   │   │   │
    │   │   │   │   ├── planning-excel/
    │   │   │   │   │   └── planning-excel.component...
    │   │   │   │   │
    │   │   │   │   ├── planning-monthly/
    │   │   │   │   │   └── planning-monthly.component...
    │   │   │   │   │
    │   │   │   │   ├── planning-snippt/
    │   │   │   │   │   └── planning-snippt.component...
    │   │   │   │   │
    │   │   │   │   ├── planning-widget/
    │   │   │   │   │   └── planning-widget.component...
    │   │   │   │   │
    │   │   │   │   ├── planning.component...
    │   │   │   │   └── planning.module.ts
    │   │   │   │
    │   │   │   ├── energy-management.module.ts
    │   │   │   ├── energy-management.service.ts
    │   │   │   ├── http-interceptor.service.ts
    │   │   │   ├── idevice.ts
    │   │   │   ├── isensor.ts
    │   │   │   ├── pagination.ts
    │   │   │   └── snackbar.service.ts
    │   │   │
    │   │   ├── forms/
    │   │   │   ├── basic-form/
    │   │   │   │   └── basic-form.component...
    │   │   │   │
    │   │   │   ├── file-upload/
    │   │   │   │   └── file-upload.component...
    │   │   │   │
    │   │   │   ├── rich-text-editor/
    │   │   │   │   └── rich-text-editor.component...
    │   │   │   │
    │   │   │   ├── wizard/
    │   │   │   │   └── wizard.component...
    │   │   │   │
    │   │   │   ├── forms.module.ts
    │   │   │   └── forms.routing.ts
    │   │   │
    │   │   ├── gateways/
    │   │   │   ├── add-gateway/
    │   │   │   │   └── add-gateway.component...
    │   │   │   │
    │   │   │   ├── gateways-ngx-table/
    │   │   │   │   ├── gateways-ngx-table.component.html
    │   │   │   │   └── gateways-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── groups/
    │   │   │   │   ├── add-group/
    │   │   │   │   │   └── add-group.component...
    │   │   │   │   │
    │   │   │   │   └── groups-ngx-table
    │   │   │   │       ├── groups-ngx-table.component.html
    │   │   │   │       └── groups-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── preview-data-dailog/
    │   │   │   │   └── preview-data-dialog.component...
    │   │   │   │
    │   │   │   ├── gateways-resolver.service.ts
    │   │   │   ├── gateways.module.ts
    │   │   │   ├── gateways.routing.ts
    │   │   │   ├── gateways.service.ts
    │   │   │   └── groups-resolver.service.ts
    │   │   │
    │   │   ├── generic-module/
    │   │   │   ├── generic-alarm-notification/
    │   │   │   │   ├── generic-alarm-notification.component...
    │   │   │   │   └── generic-alarm-notification.module.ts
    │   │   │   │
    │   │   │   ├── generic-alarms/
    │   │   │   │   ├── generic-alarms-list/
    │   │   │   │   │   └── generic-alarms-list.component...
    │   │   │   │   │
    │   │   │   │   ├── generic-define-alarms/
    │   │   │   │   │   └── generic-define-alarms.component...
    │   │   │   │   │
    │   │   │   │   └── generic-alarms.module.ts
    │   │   │   │
    │   │   │   ├── generic-devices/
    │   │   │   │   ├── generic-define-device/
    │   │   │   │   │   └── generic-define-device.component...
    │   │   │   │   │
    │   │   │   │   ├── generic-devices-list/
    │   │   │   │   │   └── generic-devices-list.component...
    │   │   │   │   │
    │   │   │   │   └── generic-devices.module.ts
    │   │   │   │
    │   │   │   ├── generic-history/
    │   │   │   │   └── generic-history.component...
    │   │   │   │
    │   │   │   ├── generic-module.routing.ts
    │   │   │   ├── generic-module.module.ts
    │   │   │   ├── generic.service.ts
    │   │   │   └── pagination.ts
    │   │   │
    │   │   ├── home/
    │   │   │   ├── home.component.html
    │   │   │   ├── home.component.ts
    │   │   │   ├── home.module.ts
    │   │   │   └── home.routing.ts
    │   │   │
    │   │   ├── map/
    │   │   │   ├── map.component...
    │   │   │   ├── map.module.ts
    │   │   │   └── map.routing.ts
    │   │   │
    │   │   ├── others/
    │   │   │   ├── app-blank/
    │   │   │   │   └── app-blank.component...
    │   │   │   │
    │   │   │   ├── others.module.ts
    │   │   │   └── others.routing.ts
    │   │   │
    │   │   ├── projects/
    │   │   │   ├── add-projects/
    │   │   │   │   └── add-projects.component...
    │   │   │   │
    │   │   │   ├── business/
    │   │   │   │   └── business.component...
    │   │   │   │
    │   │   │   ├── business-ngx-table/
    │   │   │   │   ├── business-ngx-table.component.html
    │   │   │   │   └── business-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── council/
    │   │   │   │   └── council.component...
    │   │   │   │
    │   │   │   ├── council-ngx-table/
    │   │   │   │   ├── council-ngx-table.component.html
    │   │   │   │   └── council-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── projects-ngx-table/
    │   │   │   │   ├── projects-ngx-table.component.html
    │   │   │   │   └── projects-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── projects-resolver.service.ts
    │   │   │   ├── projects.module.ts
    │   │   │   ├── projects.routing.ts
    │   │   │   └── projects.service.ts
    │   │   │
    │   │   ├── sensors/
    │   │   │   ├── add-provider/
    │   │   │   │   └── add-provider.component...
    │   │   │   │
    │   │   │   ├── add-sensor/
    │   │   │   │   └── add-sensor.component...
    │   │   │   │
    │   │   │   ├── provider-ngx-table/
    │   │   │   │   ├── provider-ngx-table.component.html
    │   │   │   │   └── provider-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── sensor-message/
    │   │   │   │   └── sensor-message.component...
    │   │   │   │
    │   │   │   ├── sensors-ngx-table/
    │   │   │   │   ├── sensors-ngx-table.component.html
    │   │   │   │   └── sensors-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── types/
    │   │   │   │   ├── add-type/
    │   │   │   │   │   └── add-type.component...
    │   │   │   │   │
    │   │   │   │   ├── payload-input-add/
    │   │   │   │   │   ├── payload-input-add.component...
    │   │   │   │   │   └── payload-input-add.module.ts
    │   │   │   │   │
    │   │   │   │   ├── payload-meter-add/
    │   │   │   │   │   ├── payload-meter-add.component...
    │   │   │   │   │   └── payload-meter-add.module.ts
    │   │   │   │   │
    │   │   │   │   └── types-ngx-table/
    │   │   │   │       ├── types-ngx-table.component.html
    │   │   │   │       └── types-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── sensor-resolver.service.ts
    │   │   │   ├── sensors.module.ts
    │   │   │   ├── sensors.routing.ts
    │   │   │   ├── sensors.service.ts
    │   │   │   └── type-resolver.service.ts
    │   │   │
    │   │   ├── servers/
    │   │   │   ├── add-server/
    │   │   │   │   └── add-server.component...
    │   │   │   │
    │   │   │   ├── servers-ngx-table/
    │   │   │   │   ├── servers-ngx-table.component.html
    │   │   │   │   └── servers-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── servers.module.ts
    │   │   │   ├── servers.routing.ts
    │   │   │   ├── servers.service.ts
    │   │   │   └── servers-resolver.service.ts
    │   │   │
    │   │   ├── sessions/
    │   │   │   ├── error/
    │   │   │   │   └── error.component...
    │   │   │   │
    │   │   │   ├── forgot-password/
    │   │   │   │   └── forgot-password.component...
    │   │   │   │
    │   │   │   ├── lockscreen/
    │   │   │   │   └── lockscreen.component...
    │   │   │   │
    │   │   │   ├── not-found/
    │   │   │   │   └── not-found.component...
    │   │   │   │
    │   │   │   ├── signin/
    │   │   │   │   └── signin.component...
    │   │   │   │
    │   │   │   ├── signin2/
    │   │   │   │   └── signin2.component...
    │   │   │   │
    │   │   │   ├── signin3/
    │   │   │   │   └── signin3.component...
    │   │   │   │
    │   │   │   ├── signin4/
    │   │   │   │   └── signin4.component...
    │   │   │   │
    │   │   │   ├── signup/
    │   │   │   │   └── signup.component...
    │   │   │   │
    │   │   │   ├── signup2/
    │   │   │   │   └── signup2.component...
    │   │   │   │
    │   │   │   ├── signup3/
    │   │   │   │   └── signup3.component...
    │   │   │   │
    │   │   │   ├── signup4/
    │   │   │   │   └── signup4.component...
    │   │   │   │
    │   │   │   ├── sessions.module.ts
    │   │   │   └── sessions.routing.ts
    │   │   │
    │   │   ├── tables/
    │   │   │   ├── filter-table/
    │   │   │   │   └── filter-table.component...
    │   │   │   │
    │   │   │   ├── fullscreen-table/
    │   │   │   │   └── fullscreen-table.component...
    │   │   │   │
    │   │   │   ├── material-table/
    │   │   │   │   └── material-table.component...
    │   │   │   │
    │   │   │   ├── paging-table/
    │   │   │   │   └── paging-table.component...
    │   │   │   │
    │   │   │   ├── sessions.module.ts
    │   │   │   └── sessions.routing.ts
    │   │   │
    │   │   ├── users/
    │   │   │   ├── add-user/
    │   │   │   │   └── add-user.component...
    │   │   │   │
    │   │   │   ├── users-ngx-table/
    │   │   │   │   ├── users-ngx-table.component.html
    │   │   │   │   └── users-ngx-table.component.ts
    │   │   │   │
    │   │   │   ├── users-resolver.service.ts
    │   │   │   ├── users.module.ts
    │   │   │   ├── users.routing.ts
    │   │   │   └── users.service.ts
    │   │   │
    │   │   └── water-module/
    │   │       ├── general/
    │   │       │   ├── add-municipality/
    │   │       │   │   └── add.municipality.component...
    │   │       │   │
    │   │       │   ├── municipality-canon-define/
    │   │       │   │   └── municipality-canon-define.component...
    │   │       │   │
    │   │       │   ├── municipality-canon-list/
    │   │       │   │   └── municipality-canon-list.component...
    │   │       │   │
    │   │       │   ├── municipality-list/
    │   │       │   │   └── municipality-list.component...
    │   │       │   │
    │   │       │   ├── municipality-terms-condition-add/
    │   │       │   │   └── municipality-terms-condition-add.component...
    │   │       │   │
    │   │       │   ├── municipality-terms-condition-list/
    │   │       │   │   └── municipality-terms-condition-list.component...
    │   │       │   │
    │   │       │   ├── municipality-contador-add/
    │   │       │   │   └── municipality-contador-add.component...
    │   │       │   │
    │   │       │   ├── municipality-contador-list/
    │   │       │   │   └── municipality-contador-list.component...
    │   │       │   │
    │   │       │   ├── municipality-consumption-block-add/
    │   │       │   │   └── municipality-consumption-block-add.component...
    │   │       │   │
    │   │       │   ├── municipality-consumption-block-list/
    │   │       │   │   └── municipality-consumption-block-list.component...
    │   │       │   │
    │   │       │   ├── municipality-diameters-add/
    │   │       │   │   └── municipality-diameters-add.component...
    │   │       │   │
    │   │       │   ├── municipality-diameters-list/
    │   │       │   │   └── municipality-diameters-list.component...
    │   │       │   │
    │   │       │   ├── municipality-inversiones-add/
    │   │       │   │   └── municipality-inversiones-add.component...
    │   │       │   │
    │   │       │   ├── municipality-inversiones-list/
    │   │       │   │   └── municipality-inversiones-list.component...
    │   │       │   │
    │   │       │   ├── municipality-service-fee-add/
    │   │       │   │   └── municipality-service-fee-add.component...
    │   │       │   │
    │   │       │   ├── municipality-service-fee-list/
    │   │       │   │   └── municipality-service-fee-list.component...
    │   │       │   │
    │   │       │   ├── municipality-sewer-rate-add/
    │   │       │   │   └── municipality-sewer-rate-add.component...
    │   │       │   │
    │   │       │   ├── municipality-sewer-rate-list/
    │   │       │   │   └── municipality-sewer-rate-list.component...
    │   │       │   │
    │   │       │   └── water-general.service.ts
    │   │       │
    │   │       ├── water-alarms/
    │   │       │   ├── water-alarms-list/
    │   │       │   │   └── water-alarms-list.component...
    │   │       │   │
    │   │       │   ├── water-define-list/
    │   │       │   │   └── water-alarms-list.component...
    │   │       │   │
    │   │       │   └── water-alarms.module.ts
    │   │       │
    │   │       ├── water-alarm-notification/
    │   │       │   ├── water-alarm-notification.component...
    │   │       │   └── water-alarm-notification.module.ts
    │   │       │
    │   │       ├── water-bill/
    │   │       │   ├── water-bill-add/
    │   │       │   │   └── water-bill-add.component...
    │   │       │   │
    │   │       │   ├── water-bill-generate/
    │   │       │   │   └── water-bill-generate.component...
    │   │       │   │
    │   │       │   ├── water-bill-list/
    │   │       │   │   └── water-bill-list.component...
    │   │       │   │
    │   │       │   └── water-bill.module.ts
    │   │       │
    │   │       ├── water-devices/
    │   │       │   ├── water-define-device/
    │   │       │   │   └── water-define-device.component...
    │   │       │   │
    │   │       │   ├── water-device-download-popup/
    │   │       │   │   └── water-device-download-popup.component...
    │   │       │   │
    │   │       │   ├── water-devices-list/
    │   │       │   │   └── water-devices-list.component...
    │   │       │   │
    │   │       │   └── water-devices.module.ts
    │   │       │
    │   │       ├── water-group/
    │   │       │   ├── water-group-add/
    │   │       │   │   └── water-group-add.component...
    │   │       │   │
    │   │       │   ├── water-group-listing/
    │   │       │   │   └── water-group-listing.component...
    │   │       │   │
    │   │       │   └── water-devices.module.ts
    │   │       │
    │   │       ├── water-history/
    │   │       │   └── water-history.component...
    │   │       │
    │   │       ├── water-list-filter/
    │   │       │   └── water-list-filter.component...
    │   │       │
    │   │       ├── water-map/
    │   │       │   └── water-map.component...
    │   │       │
    │   │       ├── water-observations/
    │   │       │   └── water-observations.component...
    │   │       │
    │   │       ├── water-popup/
    │   │       │   └── water-popup.component...
    │   │       │
    │   │       ├── water-users/
    │   │       │   ├── water-user-define/
    │   │       │   │   └── water-user-define.component...
    │   │       │   │
    │   │       │   ├── water-user-list/
    │   │       │   │   └── water-user-list.component...
    │   │       │   │
    │   │       │   ├── water-user-view/
    │   │       │   │   └── water-user-view.component...
    │   │       │   │
    │   │       │   └── water-user.module.ts
    │   │       │
    │   │       ├── pagination.ts
    │   │       ├── water-module-routing.ts
    │   │       ├── water-module.module.ts
    │   │       └── water.service.ts
    │   │
    │   ├── shared/
    │   │   └── services/
    │   │       ├── app-confirm/
    │   │       │   ├── app-confirm.component.ts
    │   │       │   └── app-confirm.service.ts
    │   │       │
    │   │       ├── app-loader/
    │   │       │   ├── app-loader.component...
    │   │       │   └── app-loader.service.ts
    │   │       │
    │   │       ├── auth/
    │   │       │   ├── auth.guard.ts
    │   │       │   └── auth.service.ts
    │   │       │
    │   │       ├── api.service.ts
    │   │       ├── copier.service.ts
    │   │       ├── customizer.service.ts
    │   │       ├── error-handler.service.ts
    │   │       ├── excel-export.service.ts
    │   │       ├── landing-page.service.ts
    │   │       ├── layout.service.ts
    │   │       ├── match-media.service.ts
    │   │       ├── navigation.service.ts
    │   │       ├── rolepermission.service.ts
    │   │       ├── route-parts.service.ts
    │   │       └── theme-service.ts
    │   │
    │   ├── app.component.html
    │   ├── app.component.css
    │   ├── app.component.ts
    │   ├── app.module.ts
    │   └── app.routing.ts
    │
    ├── assets/
    ├── enviroments/
    ├── vendor/
    ├── index.html
    ├── styles.css
    ├── main.ts
    └── polyfills.ts
```

The platform is divided in two sections: `Network Management` and `Modules`.

The `Network Management` section is used to manage Lora servers, gateways, sensors and cloud servers.

The `Modules` section is also divided into different modules for each feature that the client has hired.

# **Network management**

In this section, the client can manage general aspects that are common for each module. It is accesible in the top part of the side menu.

<p align="center">
    <img width="400" src="https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/Captura%20de%20pantalla%202021-07-19%20a%20las%2013.14.23.png?raw=true">
</p>

## **Network server**

`Network servers` send data from `sensors` to `cloud servers`. This components can also have assigned a `gateway`. There are two types of `Network servers`: **Embedded** and **Centralized**.

`Embedded network servers` are incorporated in the gateway, so, the number of N.S are equal to the sum of gateways.

On the other hand, `Centralized network servers` are separated of the gateway, so, there can be any number of NS assigned to all the gateways.

<p align="center">
    <img width="75%" src="https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/server1.png?raw=true">
</p>

## **Gateways**

`Gateways` have different `sensors` assigned. This components connect this `sensors` with a `network server` (embedded or centralized).

In `Gateways` section, the client can see a list with all gateways created with some information about each gateway like status, mac or name. Here, the client can also create new gateways and assign it a network server and some sensors.

This components can also be assigned to a group of gateways.

<p align="center">
    <img width="75%" src="https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/gateway.png?raw=true">
</p>

## **Sensors**

`Sensors` take data from the place where they have been installed and send it to a `gateway`. There are the following base type of sensors: **Wifi**, **Ibox**, **OEM** and **Custom**. Clients can also add new sensor types inheriting the basic types.

<p align="center">
    <img width="75%" src="https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/sensors.png?raw=true">
</p>

## **Projects**

`Projects` section is divided in three parts: **Projects**, **Business** and **Councils**.

In **Projects**, clients can see a list of projects and define new ones. In **Business**, clients can create different commerces and assign them to a project. In **Councils**, clients can add new areas and assign them to different projects.

## **Users**

In this section, the client can see the list of users that has created and add new users. Module permission and projects can be assigned to a user.

<p align="center">
    <img width="75%" src="https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/users.png?raw=true">
</p>

# **Modules**

There are different types of modules: `Water module`, `Public lighting module`, `Door module`, `Capacity module`, `Irrigation module`, `Boiler module` and `Generic module`


## **Boiler module**

`Boiler module` is focused on the management of boilers and the characteristics related to them. There are different features in this module:

### **Boiler devices**

Boiler device is the main concept of this module. The fields of a boiler device are:

| Fields          | Required |            Description                   |
| --------------- | :------: | :-------------------------------------:  |
| User            |    ✓     |    Id of the user related to device     |
| Name            |    ✓     |        The name of the device           |
| Description     |    ✓     |    Brief explanation of the device      |
| Mode            |    ✓     |  Selected mode 'Schedule' or 'manual'   |
| Schedule        |    ✕     | On/off boiler schedule (if not manual)  |
| Sensor          |    ✓     |      Sensor assigned to the device      |
| Rele status     |    ✕     |          Boiler relay status            |
| Longitude       |    ✕     |  Last longitude measured by the sensor  |
| Temperature     |    ✕     | Last temperature measured by the sensor |
| Update time     |    ✕     |    Last time the boiler was updated     |
| Length          |    ✓     |             Boiler length               |
| Width           |    ✓     |             Boiler width                |
| Heigth          |    ✓     |             Boiler heigth               |

On this section, there is a list of boilers and some functionalities like create/edit new devices, on/off boiler manually.


## **Irrigation module**

`Irrigation module` is focused on the management of irrigation devices and the characteristics related to them. There are different features in this module:

### **Irrigation devices**

Boiler device is the main concept of this module. The fields of a boiler device are:

| Fields          | Required |            Description                   |
| --------------- | :------: | :-------------------------------------:  |
| User            |    ✓     |    Id of the user related to device     |
| Name            |    ✓     |        The name of the device           |
| Description     |    ✓     |    Brief explanation of the device      |
| Sentilo name    |    ✓     |     Name of the device on sentilo       |
| Latitude        |    ✕     |        Device location latitude         |
| Longitude       |    ✓     |        Device location longitude        |
| Status          |    ✕     |              Device status              |
| Type            |    ✕     |           Irrigation device type        |
| Sensor          |    ✓     |      Sensor assigned to the device      |
| AuthToken       |    ✓     |            Sentilo auth token           |
| Provider        |    ✓     |             Sentilo provider            |
| Humidity limit  |    ✓     |  Humidity imit that triggers device off |

Boiler devices have soil sensors
'This feature will be developed on future'

And valves

| Fields          | Required |            Description                   |
| --------------- | :------: | :-------------------------------------:  |
| Name            |    ✓     |        Device location longitude        |
| Description     |    ✓     |    Brief explanation of the device      |
| Irrig device    |    ✓     |         Irrigation parent device        |
| Sensor          |    ✓     |      Sensor assigned to the device      |
| Index           |    ✓     |     Valve index number (starts on 1)    |
| Intervals       |    ✕     |             On/off schedule             |
| Status          |    ✕     |              Sensor status              |
| Soil sensor     |    ✕     |      Soil sensor related to valve       |

We can add a sensor to measure temperature and humidity of the device. This info is stored on irrigation_device_history_lora.



On this section, there is a list of boilers and some functionalities like create/edit new devices, on/off boiler manually.


## **Water module**

`Water module` is the section focused on the management of water devices and the characteristics related to them. There are different features in this module:

### **General**

On this section of the water module, there are the features to manage the municipalities having this module hired, the fees that they have and the diameters used. There are 8 functionalities: `Municipalities`, `Diameters`, `Service fees`, `Consumption block`, `Sewer rate`, `Canon`, `Counters` and `Investments`.

- **Municipalities:** Contains a table with all the municipalities that the user can manage.

- **Diameters:** Water devices are connected to pipes. Depending on the diameter of this pipe, there will be more or less water consumption. The user can define diameter ranges and add them to a municipality.

- **Service fees:** Assign a tariff per month and a tax rate to a diameter.
- **Sewer rate:** Define the use (industrial, commercial or domestic), the fixed fee, the consume (€/m3) and the tax rate of a sewerage plan.

- **Canons:** Define canons assigning them a tariff and a tax rate.
- **Counter:** Assign a tariff to a diameter range of a municipality.

### **Water devices**

Water device is the main concept of this module. The fields of a water device are:

| Fields          | Required |            Description            |
| --------------- | :------: | :-------------------------------: |
| Contract number |    ✕     |   Number assigned to the device   |
| Name            |    ✓     |      The name of the device       |
| Municipality    |    ✓     |  Town where device was installed  |
| Description     |    ✕     |  Brief explanation of the device  |
| Water group     |    ✕     |     Group of devices assigned     |
| User            |    ✕     |    User assigned to the device    |
| Sensor          |    ✓     |   Sensor assigned to the device   |
| Variable        |    ✓     |  Variable of the sensor assigned  |
| Water units     |    ✕     | Unit of volume used in the device |
| Diameter        |    ✕     |       Device pipe diameter        |
| Address         |    ✕     | Place where device was installed  |

On this section, there is a list of water devices and some functionalities like create new devices, download documents or generate bills. It is the core of the water module. Water devices can be grouped in `water groups`. You can generate 4 different documents in the water devices page:

- **Excel:** Save the selected water devices and fields in a [Excel formatted](https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/excel.xlsx?raw=true) document.

- **Bill:** Generate a bill with the selected water devices.

- **Dival's XML:** Save the selected water devices in a [Valencia Council formatted XML](https://github.com/sheshsingh/swat_gesinen/blob/master/.github/images/dival.xml?raw=true) document.

- **SEPA XML:** Select a generated bill to download a [SEPA XML formatted]() document.

Another important feature here is the water alarm management. The client can create different types of water alarms: `Over value`, `Lower value`, `Reverse mounting`, `Daily`, `Weekly` and `Monthly`.

- **Over value:** Alarm is activated when the sensor takes a measurement above the value specified in the alarm.

- **Lower value:** This alarm is activated when the measurement taken by the sensor is lower than the value specified by the client for this alarm.

- **Reverse mounting:** A common error when the technician install the sensor is that it can be installed backwards. The problem is that we don't know if the sensor is installed correctly. The purpose of `Reverse mounting` alarm is send a notification when a specified number of consecutive values are lower than the previous one.

- **Daily:** This alarm is active for one day and it sends a notification if a measurement is over the value defined in the alarm.

- **Weekly:** This alarm is active for one week and it sends a notification if a measurement is over the value defined in the alarm.

- **Monthly:** This alarm is active for one month and it sends a notification if a measurement is over the value defined in the alarm.

### **Water users**

Water users are accounts are used to manage bills. The client can create new users using a form divided in 4 sections: `Basic info`, `Address`, `Bank info` and `Documents`.

| Fields              |  Section   | Required | Description                            |
| ------------------- | :--------: | :------: | -------------------------------------- |
| First name          | Basic info |    ✓     | Name of the user                       |
| Last name           | Basic info |    ✕     | Surname of the user                    |
| Email               | Basic info |    ✕     | Email of the user                      |
| Mobile              | Basic info |    ✕     | Mobile phone                           |
| Municipality        | Basic info |    ✓     | Municipality to which the user belongs |
| Date of birth       | Basic info |    ✕     | Birthday of the user                   |
| Date of creation    | Basic info |    ✕     | Date when the user account was created |
| NIF                 | Basic info |    ✕     | Number of tax identification           |
| House number        |  Address   |    ✕     | Number of user's house                 |
| Street              |  Address   |    ✕     | Street address                         |
| Address             |  Address   |    ✕     | User address                           |
| City                |  Address   |    ✕     | User city                              |
| State               |  Address   |    ✕     | User state                             |
| Country             |  Address   |    ✕     | User country                           |
| Bank name           | Bank info  |    ✓     | Name of the user's bank                |
| Bank address        | Bank info  |    ✕     | Address of the user's bank             |
| IBAN                | Bank info  |    ✕     | Bank account number                    |
| Profile image       | Documents  |    ✕     | User's avatar                          |
| DNI                 | Documents  |    ✕     | User's National ID number              |
| Account certificate | Documents  |    ✕     | User's certificate                     |
| SEPA                | Documents  |    ✕     | SEPA                                   |
| ID proof            | Documents  |    ✕     | Id proof                               |

# **Deployment**

To use this Angular code in the production server, you must compile the code first using this command:

```
ng build --prod
```

If you get a memory space error, you can use the following command:

```
node --max_old_space_size=8192 node_modules/@angular/cli/bin/ng build --prod
```

Then you should use a FTP client to enter in `82.223.50.35` using the port `22`. The compiled angular files goes in `swat-gesinen/dist` folder:

```
var/
├── www/
│   └── html/
│       └── swat-gesinen/
│           └── dist/
│               └──  // here are the files
...
```

# **License**
All the code in this repository is owned by [Gesinen](https://www.gesinen.com/). <br>
Copyright © 2021, Gesinen.
