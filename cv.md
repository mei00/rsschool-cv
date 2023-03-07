# Sergey Shvalev
### `Full-Stack Developer`

### Contact information:

[LinkedIn](https://t.me/meiaum)<br>
[LinkedIn](https://www.linkedin.com/in/sergei-shvalev-0a5bb6232/)<br>
[GitHub](https://github.com/mei00)<br>

***

### About me:

I’m a 10 years experienced Full-Stack Web Developer mostly specializing in back-end who’s now exploring a new horizons of front-end development: modern JavaScript frameworks, tools, approaches and conventions. I'm looking to enhance my professional experience with an IT company specializing in hi-end web and mobile apps.

***

**Technologies & Frameworks:** JavaScript, React / React Native, Vue, Jest, HTML, CSS, SCSS, BEM, Webpack

**Additional:** Git, SOLID, OOP, FP, API & Architecture, Jira. My server side background is PHP, Laravel, MySQL.

***

### Sample code:

```js
const BASE_URL = process.env.REACT_APP_BASE_URL;

const routeCampsitesData = {
  route: routeId,
  campsites: campsites,
};
axios.post(BASE_URL + '/api/route/update_route_campsites', routeCampsitesData, ApiHelper.getRequestConfig(authToken))
  .then(res => {
    if (res.data.success) {
      dispatch(updateRoute(res.data.routeData));

      const points = RouteHelper.getPoints(res.data.routeData.campsites)
      mapRef.current.findRoute(points, ['car'], (event) => {
        let routePathData = {
          route: routeId,
          distance: event.route.distance,
          time: event.route.time,
          path: mapRoute.sections,
        };
        axios.post(BASE_URL + '/api/route/add_path_to_route', routePathData, ApiHelper.getRequestConfig(authToken))
          .then(res => {
            if (res.data.routeData) {
              dispatch(updateRoute(res.data.routeData));
            }
          })
      });

      Toast.show({
        type: 'success',
        text1: res.data.text,
      });

    }
  })
  .catch((error) => {

    if (error.response) {
      Toast.show({
        type: 'success',
        text: error.response.data.text,
      });
    }

  })

```

